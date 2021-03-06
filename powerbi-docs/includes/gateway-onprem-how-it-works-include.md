## <a name="how-the-gateway-works"></a>So funktioniert das Gateway
![So-funktioniert-das-lokale-datengateway](./media/gateway-onprem-how-it-works-include/on-prem-data-gateway-how-it-works.png)

Sehen wir uns zunächst an, was geschieht, wenn ein Benutzer mit einem Element interagiert, das mit einer lokalen Datenquelle verbunden ist. 

> [!NOTE]
> Für Power BI müssen Sie eine Datenquelle für das Gateway konfigurieren.

1. Eine Abfrage wird vom Clouddienst zusammen mit den verschlüsselten Anmeldeinformationen für die lokale Datenquelle erstellt und an die Warteschlange für die Bearbeitung durch das Gateway gesendet.
2. Die Abfrage wird daraufhin vom Gatewayclouddienst analysiert und die Anforderung mithilfe von Push an [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview/) übertragen.
3. Das lokale Datengateway fragt Azure Service Bus für ausstehende Anforderungen ab.
4. Das Gateway ruft die Abfrage ab, entschlüsselt die Anmeldeinformationen und stellt unter Verwendung dieser Anmeldeinformationen eine Verbindung mit der Datenquelle bzw. den Datenquellen her.
5. Das Gateway sendet die Abfrage zur Ausführung an die Datenquelle.
6. Die Ergebnisse werden von der Datenquelle zurück an das Gateway und anschließend weiter an den Clouddienst gesendet. Der Dienst verwendet dann die Ergebnisse.

