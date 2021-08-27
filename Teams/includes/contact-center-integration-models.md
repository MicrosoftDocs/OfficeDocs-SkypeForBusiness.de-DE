## <a name="integration-models-for-solution-providers"></a>Integrationsmodelle für Lösungsanbieter

<a name="steps"></a>

Als Kontaktcenter-Lösungsanbieter können Sie aus drei Modellen auswählen, aus der Sie Ihre verbundene Kontaktcenter-Lösung in ihre Teams:

- Wenn Sie zertifizierte SBCs und Direct Routing verwenden möchten, um eine Kontaktcenterlösung mit einem Teams verbinden möchten, finden Sie Verbinden [Modell.](?tabs=connect#steps)

- Wenn Sie Azure-Bots und die Microsoft Graph Communication-APIs verwenden möchten, um Lösungsanbietern das Erstellen von Teams-Apps zu ermöglichen, lesen Sie das Erweitern des [Modells.](?tabs=extend#steps)

- Wenn Sie ein SDK verwenden möchten, das Lösungsanbietern das Einbetten nativer Teams ihrer App ermöglicht, lesen Sie das [Power-Modell.](?tabs=power#steps) Power Solutions sind möglich, wenn das SDK gegen Ende 2021 verfügbar ist.

### <a name="the-connect-model"></a>[**Das Verbinden Modell**](#tab/connect)

Das Verbinden-Modell verwendet von Microsoft zertifizierte SBCs und Direct Routing, um Contact Center-Lösungen mit der Teams Phone System-Infrastruktur zu verbinden, wodurch erweiterte Informationen zu Routing, Konfiguration und System ermöglicht werden.

Agents können automatisierte virtuelle Assistenten und qualifikationsbasierte Routingwarteschlangen einrichten, um Informationen zu sammeln und Kunden mit Fachleuten zu verbinden.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Office 365 für Agents, über den integrierten CCaaS-Client eine Verbindung mit ihrem Microsoft-Mandanten herzustellen 

  - Sehen Sie, wann Agents mit ihrer Teams

  - Übertragungen und Gruppenanrufunterstützung mit Teams 

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - SIP-Trunking mit mehreren Mandanten zur Unterstützung mehrerer Kunden mit SBC des Lösungsanbieters.  

  - Lösungsanbieter für die Verwendung des [ <span class="underline">zertifizierten Microsoft-Session Border-Controllers (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**Das Erweiterungsmodell**](#tab/extend)

Das Erweiterungsmodell ist in den Teams-Client [](/microsoftteams/platform/overview)integriert, indem die Teams-Clientplattform , [Teams Graph-APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) und [CloudKommunikations-API in Microsoft Graph.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Das Erweiterungsmodell verwendet außerdem das Teams-Telefonsystem für alle Anruf- und Anrufsteuerungserfahrungen im Kontaktcenter, und der Kontaktcenter-Lösungsanbieter fungiert als Telefonieanbieter neben Microsoft 365.

Agents können Teams für interne Zusammenarbeit und externe Kommunikation verwenden und von dynamischen kontextbezogenen Notizen profitieren, die Daten aus mehreren Systemen korrelieren, bevor sie einen Einsatz starten, und dann aufwendige Kontextwechsel vermeiden.

Organisationen können Workflows und erweiterte Routingkonfigurationen bis hin zur einzelnen Person entwerfen und die Qualität ihres Systems und der Interaktionen messen.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - Teams-basierte App für Agentenerfahrungen 

  - Teams als primären Anrufendpunkt für die Agents 

  - Teams von Clientanrufen für alle Anrufsteuerelemente

  - Agent Experience-App für Teams web- und mobilen Client

  - Analysen, Workflowverwaltung, rollenbasierte Erfahrungen für Agents in der CCaaS-App in Teams

  - Integrierte Chat- und Zusammenarbeitserfahrungen in Teams Clients 

  - Erhalten der Leistung und Qualität Teams Bespielung des Clients in allen Apps  

### <a name="the-power-model"></a>[**Das Power-Modell**](#tab/power)

Das Power-Modell ermöglicht Lösungsanbietern das Erstellen nativer Azure-basierter Sprachanwendungen mithilfe der Teams-Anrufinfrastruktur und Clientplattform, um moderne, intelligente Lösungen für die Kunden- und Agent-Verbindung in Zusammenarbeit zu liefern. Das Ziel des Power-Modells ist die Bereitstellung einer One-App-, One-Screen-Kontaktcenter-Erfahrung.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Formelle Agentenerfahrungen, die nativ für die Kommunikation über den Mobilfunkkanal über das Teams SDK aktiviert wurden 

  - Verwenden Teams-Diensten für die Zusammenarbeit zwischen Denkmitarbeitern und für Kundeninteraktionen  

  - Schnelle Bereitstellung von Clouddiensten, Bereitstellung von überall 

  - Direkte Unterhaltungssteuerung und Interaktion mit Benutzern während Teams Unterhaltungen 

>[!NOTE]
> Das Power-Modell wird Ende 2021 zur Verfügung stehen.
