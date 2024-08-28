---
---

Щоб побачити дані трасування, потрібно надіслати запити до вашої служби. Кількість запитів залежить від коефіцієнта відбору Istio і може бути налаштована за допомогою [Telemetry API](/docs/tasks/observability/telemetry/). При стандартному значенні для коефіцієнта відбору в 1% вам потрібно надіслати принаймні 100 запитів, перш ніж перші трейси стануть видимими.

Щоб надіслати 100 запитів до служби `productpage`, використовуйте наступну команду:

{{< text bash >}}
$ for i in $(seq 1 100); do curl -s -o /dev/null "http://$GATEWAY_URL/productpage"; done
{{< /text >}}