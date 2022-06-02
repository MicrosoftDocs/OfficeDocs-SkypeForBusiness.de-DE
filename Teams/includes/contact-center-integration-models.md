## <a name="integration-models-for-solution-providers"></a>Integrationsmodelle für Lösungsanbieter

<a name="steps"></a>

Als Anbieter von Contact Center-Lösungen stehen drei Modelle zur Auswahl, um Ihre verbundene Contact Center-Lösung in Teams zu integrieren:

- Wenn Sie zertifizierte SBCs und Direct Routing verwenden möchten, um eine Contact Center-Lösung mit Teams zu verbinden, lesen Sie das [Verbinden-Modell](?tabs=connect#steps).

- Wenn Sie Azure-Bots und die Microsoft Graph-Kommunikations-APIs verwenden möchten, um Lösungsanbietern das Erstellen Teams Apps zu ermöglichen, lesen Sie das [Extend-Modell](?tabs=extend#steps).

- Wenn Sie ein SDK verwenden möchten, mit dem Lösungsanbieter systemeigene Teams Erfahrungen in ihrer App einbetten können, lesen Sie das [Power-Modell](?tabs=power#steps). Power-Lösungen sind möglich, wenn das SDK verfügbar ist. Demnächst.

### <a name="the-connect-model"></a>[**Das Verbinden-Modell**](#tab/connect)

Das Verbinden-Modell verwendet von Microsoft zertifizierte SBCs und Direct Routing, um Contact Center-Lösungen mit Teams Telefonsysteminfrastruktur zu verbinden, wodurch erweiterte Routing-, Konfigurations- und Systemeinblicke ermöglicht werden.

Agenten können automatisierte virtuelle Assistenten und kompetenzbasierte Routingwarteschlangen einrichten, um Informationen zu sammeln und Kunden mit Fachexperten zu verbinden.

**Featurehighlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, umfassen die Schwerpunktbereiche Folgendes:

- Office 365 authN für Agents zum Herstellen einer Verbindung mit ihrem Microsoft-Mandanten über den integrierten CCaaS-Client

- Anzeigen, wann Agents mit Teams verfügbar sind

- Transfers und Gruppenanrufsupport mit Teams

- Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams

- Sip-Trunking mit mehreren Mandanten zur Unterstützung mehrerer Kunden auf dem SBC des Lösungsanbieters.

- Lösungsanbieter zur Verwendung des [<span class="underline">von Microsoft zertifizierten Session Border Controller (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**Das Extend-Modell**](#tab/extend)

Das Extend-Modell lässt sich mithilfe der [Teams-Clientplattform](/microsoftteams/platform/overview), [Teams Graph-APIs](/graph/api/resources/teams-api-overview) und [cloudkommunikations-API in Microsoft Graph in den](/graph/api/resources/communications-api-overview) Teams-Client integrieren. Das Extend-Modell verwendet auch das Teams-Telefonsystem für alle Anruf- und Anrufsteuerungsfunktionen im Contact Center, und der Lösungsanbieter des Contact Centers fungiert neben Microsoft 365 als Telefonieanbieter.

Agents können Teams für die interne Zusammenarbeit und externe Kommunikation verwenden und von dynamischen Kontextnotizen profitieren, die Daten aus mehreren Systemen vor dem Start eines Engagements korrelieren, und dann kostspielige Kontextwechsel vermeiden.

Organisationen können Workflows und erweiterte Routingkonfigurationen individuell entwerfen und die Qualität ihres Systems und ihrer Interaktionen messen.

**Featurehighlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, umfassen die Schwerpunktbereiche Folgendes:

- Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams

- Teams-basierte App für Agent-Erfahrungen

- Teams als primären aufrufenden Endpunkt für die Agents

- Teams client calling for all the call controls

- Agent experience app for both Teams web and mobile client

- Analysen, Workflowverwaltung, rollenbasierte Erfahrungen für Agents in der CCaaS-App in Teams

- Chat- und Zusammenarbeitserfahrungen, die in Teams Clients integriert sind

- Beibehalten der Leistung und Qualität Teams Clientumgebungen in allen Apps

### <a name="the-power-model"></a>[**Das Power-Modell**](#tab/power)

Das Power-Modell ermöglicht Es Lösungsanbietern, native Azure-basierte VoIP-Anwendungen mithilfe der Teams Anrufinfrastruktur und Clientplattform zu erstellen, um moderne, intelligente Lösungen für die Zusammenarbeit zwischen Kunden und Agenten bereitzustellen. Das Ziel des Power-Modells ist die Bereitstellung einer 1-App-Kontaktcenter-Oberfläche mit einem Bildschirm.


> [!NOTE]
> Demnächst.
