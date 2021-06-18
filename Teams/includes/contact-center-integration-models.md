## <a name="integration-models-for-solution-providers"></a>Integrationsmodelle für Lösungsanbieter

<a name="steps"></a>

Als Lösungsanbieter im Kontaktcenter gibt es drei Modelle zur Auswahl, aus der Sie Ihre verbundene Kontaktcenter-Lösung in Teams integrieren können:

- Wenn Sie zertifizierte SBCs und Direct Routing verwenden möchten, um eine Kontaktcenterlösung mit Teams zu verbinden, lesen Sie [das Connect-Modell.](?tabs=connect#steps)

- Wenn Sie Azure-Bots und die Microsoft Graph-Kommunikations-APIs verwenden möchten, um Lösungsanbietern das Erstellen von Teams-Apps zu ermöglichen, lesen Sie das Erweitern [des Modells.](?tabs=extend#steps)

- Wenn Sie ein SDK verwenden möchten, das Lösungsanbietern das Einbetten nativer Teams-Erfahrungen in ihre App ermöglicht, lesen Sie das [Power-Modell.](?tabs=power#steps) Power Solutions sind möglich, wenn das SDK gegen Ende 2021 verfügbar ist.

### <a name="the-connect-model"></a>[**Das Connect-Modell**](#tab/connect)

Das Connect-Modell verwendet microsoft-zertifizierte SBCs und Direct Routing, um Contact Center-Lösungen mit der Teams-Telefonsysteminfrastruktur zu verbinden, wodurch erweiterte Routing-, Konfigurations- und Systemerkenntnisse ermöglicht werden.

Agents können automatisierte virtuelle Assistenten und qualifikationsbasierte Routingwarteschlangen einrichten, um Informationen zu sammeln und Kunden mit Fachleuten zu verbinden.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Office 365-Authentifizierung für Agents zum Herstellen einer Verbindung mit ihrem Microsoft-Mandanten über den integrierten CCaaS-Client 

  - Sehen, wann Agents in Teams verfügbar sind

  - Übertragungen und Gruppenanrufunterstützung mit Teams 

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - SIP-Trunking mit mehreren Mandanten zur Unterstützung mehrerer Kunden mit SBC des Lösungsanbieters.  

  - Lösungsanbieter für die Verwendung des [ <span class="underline">zertifizierten Microsoft-Session Border-Controllers (SBC)</span>](../direct-routing-border-controllers.md)


### <a name="the-extend-model"></a>[**Das Erweiterungsmodell**](#tab/extend)

Das Erweiterungsmodell kann mithilfe der [](/microsoftteams/platform/overview)Teams-Clientplattform, [der Teams Graph-APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) und der [Cloudkommunikations-API in Microsoft Graph in den Teams-Client integriert werden.](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) Das Erweiterungsmodell verwendet außerdem das Teams-Telefonsystem für alle Anruf- und Anrufsteuerungserfahrungen im Kontaktcenter, und der Lösungsanbieter im Kontaktcenter fungiert neben Microsoft 365 als Telefoniebetreiber.

Agents können Teams für interne Zusammenarbeit und externe Kommunikation verwenden und von dynamischen, kontextbezogenen Notizen profitieren, die Daten aus mehreren Systemen korrelieren, bevor sie einen Einsatz starten, und dann einen kostspieligen Kontextwechsel vermeiden.

Organisationen können Workflows und erweiterte Routingkonfigurationen bis hin zur einzelnen Person entwerfen und die Qualität ihres Systems und der Interaktionen messen.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Teams Graph-APIs und Cloudkommunikations-APIs für die Integration in Teams 

  - Teams-basierte App für Agent-Erfahrungen 

  - Teams als primären Endpunkt für Anrufe für die Agents 

  - Teams-Clientanrufe für alle Anrufsteuerelemente

  - App für Agent-Erfahrung sowohl für den Webclient als auch den mobilen Teams-Client

  - Analysen, Workflowverwaltung, rollenbasierte Erfahrungen für Agents in der CCaaS-App in Teams

  - Integrierte Chat- und Zusammenarbeitserfahrungen in Teams-Clients 

  - Erhalten der Leistung und Qualität der Teams-Clienterfahrungen in allen Apps  

### <a name="the-power-model"></a>[**Das Power-Modell**](#tab/power)

Das Power-Modell ermöglicht Lösungsanbietern das Erstellen nativer Azure-basierter Sprachanwendungen mithilfe der Anrufinfrastruktur und Clientplattform von Teams, um moderne, intelligente Lösungen für die Kunden- und Agent-Verbindung für die Zusammenarbeit zu liefern. Das Ziel des Power-Modells ist die Bereitstellung einer One-App-, One-Screen-Kontaktcenter-Erfahrung.

**Feature-Highlights:**

Obwohl es sich bei diesen Features nicht um eine umfassende Liste der Featurefunktionen für dieses Integrationsmodell handelt, stehen die folgenden Schwerpunktbereiche zur Verfügung:

  - Formelle Mitarbeitererfahrungen, die nativ für die Kommunikation über den Kanal über das Teams SDK aktiviert wurden 

  - Verwenden von Teams-Diensten für die Zusammenarbeit zwischen Mitarbeiter und Kundeninteraktionen  

  - Schnelle Bereitstellung von Clouddiensten, Bereitstellung von überall 

  - Direkte Unterhaltungssteuerung und Interaktion mit Benutzern während Teams-Unterhaltungen 

>[!NOTE]
> Das Power-Modell wird Ende 2021 zur Verfügung stehen.
