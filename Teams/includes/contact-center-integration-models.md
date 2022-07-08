## <a name="integration-models-for-solution-providers"></a>Integrationsmodelle für Lösungsanbieter

<a name="steps"></a>

Als Anbieter von Contact Center-Lösungen stehen drei Modelle zur Auswahl, um Ihre verbundene Contact Center-Lösung in Teams zu integrieren:

- Wenn Sie zertifizierte SBCs und Direct Routing verwenden möchten, um eine Contact Center-Lösung mit Teams zu verbinden, lesen Sie das [Connect-Modell](?tabs=connect#steps).

- Wenn Sie Azure-Bots und die Microsoft Graph-Kommunikations-APIs verwenden möchten, um Lösungsanbietern das Erstellen von Teams-Apps zu ermöglichen, lesen Sie das [Extend-Modell](?tabs=extend#steps).

- Wenn Sie ein SDK verwenden möchten, mit dem Lösungsanbieter native Teams-Umgebungen in ihre App einbetten können, lesen Sie das [Power-Modell](?tabs=power#steps). Power-Lösungen sind möglich, wenn das SDK verfügbar ist. Demnächst.

### <a name="the-connect-model"></a>[**Das Connect-Modell**](#tab/connect)

Das Connect-Modell verwendet von Microsoft zertifizierte SBCs und Direct Routing, um Contact Center-Lösungen mit der Teams-Telefonsysteminfrastruktur zu verbinden, wodurch erweiterte Routing-, Konfigurations- und Systemerkenntnisse ermöglicht werden.

Agenten können automatisierte virtuelle Assistenten und kompetenzbasierte Routingwarteschlangen einrichten, um Informationen zu sammeln und Kunden mit Fachexperten zu verbinden.

**Featurehighlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, umfassen die Schwerpunktbereiche Folgendes:

- Office 365 authN für Agents zum Herstellen einer Verbindung mit ihrem Microsoft-Mandanten über den integrierten CCaaS-Client

- Anzeigen, wann Agents mit Teams verfügbar sind

- Übertragungen und Gruppenanruf-Support mit Teams

- Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams

- Sip-Trunking mit mehreren Mandanten zur Unterstützung mehrerer Kunden auf dem SBC des Lösungsanbieters.

- Lösungsanbieter zur Verwendung des [<span class="underline">von Microsoft zertifizierten Session Border Controller (SBC)</span>](../direct-routing-border-controllers.md)

### <a name="the-extend-model"></a>[**Das Extend-Modell**](#tab/extend)

Das Extend-Modell kann mithilfe der [Teams-Clientplattform](/microsoftteams/platform/overview), der [Teams Graph-APIs](/graph/api/resources/teams-api-overview) und der [Cloud communications-API in Microsoft Graph in](/graph/api/resources/communications-api-overview) den Teams-Client integriert werden. Das Extend-Modell verwendet auch das Teams-Telefonsystem für alle Kontaktcenteranrufe und Anrufsteuerungsfunktionen, und der Lösungsanbieter des Contact Centers fungiert neben Microsoft 365 als Telefonieanbieter.

Agents können Teams für die interne Zusammenarbeit und externe Kommunikation verwenden und von dynamischen, kontextbezogenen Notizen profitieren, die Daten aus mehreren Systemen korrelieren, bevor ein Engagement gestartet wird, und dann eine kostspielige Kontextumschaltung vermeiden.

Organisationen können Workflows und erweiterte Routingkonfigurationen individuell entwerfen und die Qualität ihres Systems und ihrer Interaktionen messen.

**Featurehighlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, umfassen die Schwerpunktbereiche Folgendes:

- Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams

- Teams-basierte App für Agent-Erfahrungen

- Teams als primären Anrufendpunkt für die Agents

- Teams-Clientanrufe für alle Anrufsteuerungen

- Agent-Benutzeroberflächen-App für Teams-Web- und Mobile-Client

- Analysen, Workflowverwaltung, rollenbasierte Erfahrungen für Agents in der CCaaS-App in Teams

- In Teams-Clients integrierte Chat- und Zusammenarbeitserfahrungen

- Erhalten der Leistung und Qualität der Teams-Clientumgebungen in allen Apps

> [!NOTE]
> Der Agent-Bot benötigt keine Telefonsystemlizenz. Der Teams-Benutzer benötigt eine Telefonsystemlizenz und eine Telefonnummer.

### <a name="the-power-model"></a>[**Das Power-Modell**](#tab/power)

Das Power-Modell ermöglicht Es Lösungsanbietern, native Azure-basierte VoIP-Anwendungen mithilfe der Teams-Anrufinfrastruktur und -Clientplattform zu erstellen, um moderne, intelligente Lösungen für die Zusammenarbeit zwischen Kunden und Agenten bereitzustellen. Das Ziel des Power-Modells ist die Bereitstellung einer 1-App-Kontaktcenter-Oberfläche mit einem Bildschirm.


> [!NOTE]
> Demnächst.
