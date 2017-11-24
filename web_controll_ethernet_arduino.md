# Control ethernet via localnetwork - Test 1.0

Simple controller arduino via ethernet module

## Source code

``` cpp
#include <SPI.h>
#include <Ethernet.h>

byte mac[] = {0x90, 0xA2, 0xDA, 0x0D, 0x48, 0xD3};

IPAddress ip(192, 168, 1, 7);
IPAddress gateway(192, 168, 1, 1);
IPAddress subnet(255, 255, 255, 0);

EthernetServer server(80);
String readString;

void setup() {

  pinMode(13, OUTPUT);

  Serial.begin(9600);

  Ethernet.begin(mac, ip, gateway, subnet);
  server.begin();
  Serial.print("Server is at ");
  Serial.println(Ethernet.localIP());
  Serial.println("Control ethernet via localnetwork - Test 1.0");
}

void loop() {
  EthernetClient client = server.available();
  if (client) {
    while (client.connected()) {
      if (client.available()) {
        char c = client.read();
        if (readString.length() < 100) {
          readString += c;
          if (c == '\n') {
            client.println("HTTP/1.1 200 OK");
            client.println("Content-Type: text/html");
            client.println();
            client.println("<html>");
            client.println("<head>");
            client.println("<title>Control ethernet via localnetwork</title>");
            client.println("</head>");
            client.println("<body>");
            client.println("<h1>Control ethernet via localnetwork</h1>");
            client.println("<hr>");
            client.println("<center>");
            client.println("<a href=\"/?on13\"\">Turn On port 13</a>");
            client.println("<br />");
            client.println("<br />");
            client.println("<a href=\"/?off13\"\">Turn Off port 13</a><br />");
            client.println("</center>");
            client.println("</body>");
            client.println("</html>");
            client.stop();
            if (readString.indexOf("?on13") > 0) {
              digitalWrite(13, HIGH);
              Serial.println("Port 13: On");
            }
            else {
              if (readString.indexOf("?off13") > 0) {
                digitalWrite(13, LOW);
                Serial.println("Port 13: Off");
              }
            }
            readString = "";
            delay(1);
          }
        }
      }
    }
  }
}
```

## Demo

See: http://192.168.1.7/

![alt text](http://i.imgur.com/tnP2M1y.png)
