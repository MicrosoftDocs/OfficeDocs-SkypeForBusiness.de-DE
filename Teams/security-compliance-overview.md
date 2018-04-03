---
title: Übersicht über Sicherheit und Compliance in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Eine Übersicht über die Sicherheits- und Compliance-Funktionen von Microsoft Teams, einschließlich Überwachung und Berichterstellung, Compliancesuche in Inhalten, eDiscovery und vielem mehr
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857e4b691256ff13b6f9308bcd9fb12dfb10297d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Übersicht über Sicherheit und Compliance in Microsoft Teams
======================================================

Microsoft Teams basiert auf der Office 365-Cloud auf Unternehmensniveau mit Hyperskalierung und bietet die erweiterten Sicherheits- und Compliance-Funktionen, die unsere Kunden erwarten.

Teams ist von der Einführung an mit Stufe C konform. Dazu gehören die folgenden Standards: ISO 27001, ISO 27018, SSAE16 SOC 1 und SOC 2, HIPAA und EU-Standardvertragsklauseln (EU Model Clauses, EUMC). Microsoft klassifiziert innerhalb des Microsoft-Compliance-Frameworks Office 365-Anwendungen und -Dienste in vier Kategorien. Jede Kategorie wird durch bestimmte Compliance-Verpflichtungen definiert, die ein Office 365-Dienst oder ein zugehöriger Microsoft-Dienst erfüllen muss, um in dieser Kategorie geführt zu werden.

Dienste in den Compliance-Kategorien C und D, für die branchenführende Compliance-Verpflichtungen gelten, sind standardmäßig aktiviert. Dienste der Kategorien A und B verfügen über Steuermöglichkeiten, mit denen diese Dienste organisationsweit aktiviert oder deaktiviert werden können. Details hierzu finden Sie im Dokument zum [Compliance-Framework für Branchenstandards und -bestimmungen](https://go.microsoft.com/fwlink/?linkid=855777). Microsoft Teams unterstützt außerdem Cloud Security Alliance-Compliance.

Teams erzwingt außerdem teamweite und organisationsweite zweistufige Authentifizierung, einmaliges Anmelden über Active Directory und Verschlüsselung der übertragenen Daten sowie der ruhenden Daten. Dateien werden in SharePoint gespeichert und mit dem entsprechenden SharePoint-Mechanismus verschlüsselt. Notizen werden in OneNote gespeichert und mit dem entsprechenden OneNote-Mechanismus verschlüsselt.

Außerdem haben wir Unterstützung für Überwachungsprotokollsuche, eDiscovery und gesetzliche Aufbewahrungspflicht für Kanäle, Chats und Dateien sowie mobile Anwendungsverwaltung mit Microsoft Intune hinzugefügt. Fahren Sie mit der Office 365-Sicherheit und Compliance Center, um diese Einstellungen verwalten. 

## <a name="auditing-and-reporting"></a>Überwachung und Berichterstellung

Die Überwachungsprotokollsuche ist direkt in das Office 365 Security & Compliance Center integriert und macht Funktionen verfügbar, mit denen Sie Warnungen festlegen und/oder Berichte zu Überwachungsereignissen erstellen können, indem Sie Exporte von arbeitsauslastungsspezifischen oder generischen Ereignissätzen für unbegrenzte Überwachungszeiträume zur Verwendung durch Administratoren und zu Untersuchungszwecken verfügbar machen. Alle Überwachungsprotokolldaten stehen zum Einrichten von Warnungen sowie zum Filtern und Exportieren zur weiteren Analyse im Office 365 Security & Compliance Center zur Verfügung.

## <a name="compliance-content-search"></a>Compliancesuche in Inhalten

Die Inhaltssuche kann verwendet werden, um Microsoft Teams mit umfangreichen Filterfunktionen zu durchsuchen. Die Inhalte können zur Unterstützung von Compliance und Rechtsstreitigkeiten in einen speziellen Container exportiert werden. Dies kann mit oder ohne eDiscovery-Fall geschehen.

## <a name="ediscovery"></a>eDiscovery

Bei eDiscovery handelt es sich um den elektronischen Aspekt beim Identifizieren, Sammeln und Erzeugen von elektronisch gespeicherten Informationen (ESI) als Reaktion auf die Aufforderung zur Vorlage dieser Informationen in einem Rechtsstreit oder einer Untersuchung.

Mögliche Fallmanagement, permanentes, Suche, Analyse und Exportieren von Daten für Teams. Dazu gehören Chat, Messaging-und Datei.

Kunden können In-Situ-eDiscovery oder [Advanced eDiscovery](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4) nutzen.

In der folgenden Tabelle sind die Unterschiede zwischen den beiden Funktionen aufgeführt:


| |In-Situ-eDiscovery  |Advanced eDiscovery  |
|---------|---------|---------|
|Fallmanagement     |X        |X         |
|Zugriffssteuerung  |X         |X         |
|Suche in Inhalten     |X         | X        |
|Speicher   |X         | X        |
|Export     |X         |X         |
|Erkennung von Duplikaten     |-         |X         |
|Relevanzsuche mit maschinellem Lernen    |-         |X         |
|Analyse unstrukturierter Daten      |-         |X         |


## <a name="legal-hold"></a>Gesetzliche Aufbewahrungspflicht

Wenn für ein Team in Microsoft Teams ein In-Situ-Speicher oder Beweissicherungsverfahren aktiviert wird, gilt dies für das Gruppenpostfach.

Gesetzliche Aufbewahrungspflicht wird im Allgemeinen im Kontext eines eDiscovery-Falls angewendet.

Die folgende Abbildung zeigt den Workflow von Teams-Daten zu Exchange und SharePoint.

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> Beim Ermitteln von Microsoft Teams-Inhalten ist eine Verzögerung von bis zu 24 Stunden möglich.


## <a name="retention-policies"></a>Aufbewahrungsrichtlinien

Teams Unterhaltungen sind beständigen und ewig standardmäßig beibehalten. Mit der Einführung von Aufbewahrungsrichtlinien können Administratoren Aufbewahrungsrichtlinien (Aufbewahrung und Löschung) in die Sicherheit und Compliance Center für Teams Chat und Channel-Nachrichten konfigurieren. Dadurch Organisationen, die Daten für die Kompatibilität (d. h., Beibehaltung der Richtlinie) für einen bestimmten Zeitraum beibehalten oder Beseitigen der Daten (d. h., Richtlinie löschen), wenn es eine Haftung nach einem bestimmten Zeitraum berücksichtigt wird. Aufbewahrungsrichtlinien Teams stellen Sie sicher, dass sie beim Löschen von Daten aus alle Speicherorte permanente Daten in der Teams Dienst entfernt wird. 

Zum Verwalten von Teams Aufbewahrungsrichtlinien Works verwenden Sie die Einstellungen und -Cmdlets im Office 365-Sicherheit und Compliance Center unter **Daten Governance** > **Aufbewahrung**.

Aufbewahrungsrichtlinien Teams unterstützen: 
    
- Permanentes: Teams Daten für eine angegebene Dauer beibehalten und nichts Unternehmen.
- Beibehaltung und dann löschen: Teams Daten für eine angegebene Dauer beibehalten, und klicken Sie dann löschen
- Löschen: Löschen von Teams Daten nach einer bestimmten Zeit

Aufbewahrungsrichtlinien Teams noch unterstützt nicht:

- Erweiterte Aufbewahrungsrichtlinien gelten nicht für Teams Chat und Teams Channel Nachricht Speicherorte
- Dauer von weniger als 30 Tagen

Administratoren können separate Aufbewahrungsrichtlinien für Teams private Chats (1:1 oder 1: n-Chats) und Teams Channel Nachrichten einrichten. In vielen Fällen sollten Organisationen private chatdaten als mehrere eine Haftung als Channel-Nachrichten, die in der Regel Weitere projektbezogenen Unterhaltungen sind. Richten Sie diese Richtlinien in der Sicherheit und Compliance Center, **Daten Governance** > **Aufbewahrung**. Schalten Sie **Teams channel Nachrichten** und **Teams chats** und definieren Sie dann die Aufbewahrungsrichtlinien für diesen Speicherorten (ebenfalls in der folgenden Abbildung dargestellt). 

Wenn Sie **Teams channel Nachrichten**aktivieren, können Sie Teams angeben, auf die diese Richtlinie angewendet wird. Beispielsweise für Teams X, Y und Z, der Administrator kann die Löschrichtlinien 1 Jahr (durch diese Teams einzeln auswählen) festgelegt, und Anwenden einer Richtlinie 3 Jahre Löschung auf den Rest der Teams. 

Das gleiche möglich für **Teams chats** , indem Sie bestimmte Benutzer auswählen und Anwenden von Aufbewahrungsrichtlinien eindeutig. 

![Diagramm des Workflows von Microsoft Teams-Daten zu Exchange und SharePoint](media/Retention-Policies.png)


> [!IMPORTANT]
> Die Speicherorte für Teams Channel-Nachricht und Teams Chats Speicherorte Adresse nur Teams Unterhaltungen in Exchange Online-Postfächer (Benutzer- und Postfächern) gespeichert. Die Nachrichten werden aus allen relevanten Speicherorte, nämlich die Postfächer, Gate und Chatdienst gelöscht. 
> 
> Verwenden Sie zum Verwalten von Aufbewahrungsrichtlinien für Teams Dateien, die in OneDrive für Unternehmen und SharePoint gespeichert sind, ihre Aufbewahrungsrichtlinien.




Konzipiert werden Löschrichtlinien für Teams Dateien über SharePoint Online und OneDrive for Business-Standorte konfiguriert. Daher ist es möglich, dass eine Richtlinie löschen konnte eine Datei in einer Nachricht Teams, Chat oder DDE-Kanal verwiesen wird, bevor diese Nachrichten gelöscht. In diesem Fall die Datei wird weiterhin in der Nachricht Teams angezeigt, aber wenn Sie die Datei klicken, erhalten Sie einen "Datei nicht gefunden"-Fehler (Dies kann auch ohne eine Richtlinie vorkommen, wenn ein Benutzer eine Datei manuell aus SharePoint Online oder OneDrive für Unternehmen löscht).


Ausführliche Informationen zur Konfiguration von Aufbewahrungsrichtlinien für Office 365 und das Lesen der [Übersicht über die Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Aufbewahrungsrichtlinien – häufig gestellte Fragen

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>Welche Arten von Richtlinien kann ich in Aufbewahrungsrichtlinien einrichten und Funktionsweise deren?

Im Sicherheit und Compliance Center Wenn Sie eine Aufbewahrungsrichtlinie für Teams oder für alle anderen Arbeitslasten einrichten können Sie zwei Haupttypen von Richtlinien einrichten: 
- Permanentes: Diese Richtlinien sicher, dass Ihre Daten für einen bestimmten Zeitraum, unabhängig davon, was, in den Tools für die Endbenutzer geschieht beibehalten werden. Sie stellen Sie sicher, dass Daten aus Gründen der Einhaltung von Bestimmungen beibehalten werden und in eDiscovery bis zu diesem Zeitpunkt verfügbar läuft ab. Nach Ablauf die Zeit kann Ihre Richtlinie angeben, ob nichts Unternehmen oder Löschen der Daten. In Teams Wenn Sie eine Beibehaltung der Richtlinie für 7 Jahre erstellen, auch wenn Endbenutzer ihre Nachrichten Teams löschen werden diese Nachrichten weiterhin für eDiscovery für 7 Jahre beibehalten.
- Löschvorgang: Diese Richtlinien sicherstellen, dass Daten keine Haftung für Ihre Organisation. Nach der angegebenen Dauer werden Daten aus allen relevanten Speicher in Teams gelöscht. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Können wir die Teams im Org geltende Richtlinien werden? 

Nein, derzeit nicht. Sie müssen bestimmte Richtlinien für Teams Chat und Channel-Nachrichten mithilfe der Teams Speicherort Zeile oder diese Teams Cmdlets erstellen: New-TeamsRetentionCompliancePolicy & New-TeamsComplianceRetentionRule. Diese Cmdlets Get haben, und legen Sie auch Versionen.

### <a name="are-these-retention-policies-retroactive"></a>Sind die folgenden Aufbewahrungsrichtlinien rückwirkende? 

Ja, Sie sind. Wenn Sie eine Aufbewahrungsrichtlinie zum Löschen von Daten, die älter als 60 Tage erstellen, wird vor mehr als 60 Tagen erstellte Teams Daten gelöscht. 

### <a name="what-is-the-default-retention-policy"></a>Was ist Standardaufbewahrungsrichtlinie? 

Standardmäßig werden Teams Chat, DDE-Kanal und Dateien Daten für immer beibehalten. Ein Benutzer kann etwas löschen, aber keine von Aufbewahrungsrichtlinien, Teams Daten werden immer in Exchange online-Postfächern (Benutzer und Gruppen) archiviert, und bleiben Sie dort für eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Kann ich Gruppen von Benutzern oder Teams in einer Richtlinie bereitgestellt? 

Ja, gehen Sie vor. Im Assistenten zum Erstellen von Richtlinien im Schritt Speicherorte können einschließen oder Ausschließen von Teams (**Teams channel Nachrichten**) oder Benutzer (**Teams Chat**) und gezielte Richtlinien für Ihre Organisation erstellen. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Was ist der Hauptunterschied zwischen der Verwendung der Gruppe Postfach Speicherort Zeile und Teams Channel Nachrichten Speicherort Zeile in Aufbewahrungsrichtlinien? 

Wenn Sie die Gruppenpostfach und Benutzer Postfach Speicherort Zeilen für Exchange Online verwenden, werden aus der angegebenen Postfächer Teams Daten gelöscht werden. Jedoch entfernt dies nur Daten aus dem Postfach. Es wird anderen Teams Daten, beispielsweise Chats Dienst nicht gelöscht. Es wird empfohlen, dass Sie Aufbewahrungsrichtlinien Teams verwenden, um alle Teams Daten ordnungsgemäß zu verwalten. Eine Aufbewahrungsrichtlinie Teams entfernt Teams Daten aus allen Speicherorten – Postfächer, Chat Speicherdienst, Teams Clients. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Was geschieht mit Skype für Business Online und Teams interop Chats – sie von Aufbewahrungsrichtlinien betroffen sind?

Ja, Skype für Business Online und Teams interop Chats die gleiche Weise arbeiten. Nachdem die Skype für Business Online Chat in Teams stammt, wird eine Meldung in einem Teams Chat Thread und ruft in das entsprechende Postfach aufgenommen. Damit die gleiche Works – flow löscht Teams Löschrichtlinien diese Nachrichten aus der Teams Thread. Jedoch ist wenn aufgezeichnete für Skype für Business Online eingeschaltet ist und aus der Skype für Business Online Clientseite die in einem Postfach gespeichert werden werden, diese chatdaten nicht durch eine Aufbewahrungsrichtlinie Teams behandelt.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Kann ich diese über Sicherheit und Compliance Center-Cmdlets? Was soll ich verwenden? 

Absolut. Sie können Teams Aufbewahrungsrichtlinien mithilfe von [Sicherheit und Compliance center Powershell-Cmdlets]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)erstellen. Denken Sie daran, dass diese nicht über Exchange Online-Cmdlets sind. Hier werden die Cmdlets, die wir für Teams erstellt haben. Sie führen Sie die vorhandenen Nomenklatur und-Art von Aufbewahrung heute verfügbaren Cmdlets Sicherheit und Compliance Center.

|Richtlinie|Regel|
|---|---|
|Neue TeamsRetentionCompliancePolicy| Neue TeamsRetentionComplianceRule|
|Get-TeamsRetentionCompliancePolicy| Get-TeamsRetentionComplianceRule|
|Get - TeamsRetentionCompliancePolicy| Set - TeamsRetentionComplianceRule|
|Remove - TeamsRetentionCompliancePolicy| Remove - TeamsRetentionComplianceRule|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>Wenn es mehrere Aufbewahrungsrichtlinien für Teams mit unterschiedlichen Dauer sind, welche wins?

Es folgen [Prinzipien von Aufbewahrungsrichtlinien](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), und es wird empfohlen, dass Sie zu tun. Die Antwort ist: 
-   Permanentes immer im Wettbewerb löschen
-   Wins-längste immer Beibehaltung der Periode
-   Ausdrückliche Inklusion im Wettbewerb implizite Inklusion im Hinblick auf Speicherorte
-   Kürzeste Löschung Period wins



## <a name="retention-policies-known-issues"></a>Aufbewahrungsrichtlinien – bekannte Probleme

1. Klicken Sie unter Wählen Sie Teams in der Zeile Teams Channel Nachrichten Speicherort sehen Sie sich, dass Office 365-Gruppen, sind nicht auch Teams. Dieses Problem wird in der Zukunft behoben werden.

1. Klicken Sie unter Wählen Sie Benutzer in der Zeile des Teams Chat Speicherort möglicherweise Gäste und nicht-Mailbox Benutzer angezeigt. Aufbewahrungsrichtlinien werden nicht vorgesehen für Gäste festgelegt werden soll, und wir arbeiten, um diese aus der Liste zu entfernen. 

1. Lebenszyklus der Exchange-Assistent (ELC) wird täglich ausgeführt, aber es wurde eine SLA von 7 Tage. Daher ist es möglich, dass, wenn Sie eine Aufbewahrungsrichtlinie Teams zum Löschen von Elementen, die älter als 60 Tage haben, diese Elemente für bis zu 67 Tage beibehalten werden konnte. Dies ist eine neue Situation nicht – es gilt das Exchange-Modell. In den meisten Fällen ist natürlich keine Verzögerung.


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?         |
|![Symbol für „Nächste Schritte“](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Nächste Schritte         |Dokumentieren der erforderlichen Features für Sicherheit und Compliance.         |

<a name="licensing"></a>Lizenzierung
---------------

Die Funktionen für den Schutz von Informationen hängen von den Office 365-Abonnements und den zugehörigen eigenständigen Lizenzen ab.

|Funktion für den Schutz von Informationen   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Enterprise E1   |Office 365 Enterprise E3/E4   |Office 365 Enterprise E5   |
|---|---|---|---|---|---|
|Archiv|-  |-   |-   |Ja   |Ja   |
|In-Situ-eDiscovery|-   |-   |-   |Ja   |Ja   |
|Advanced eDiscovery|-   |-   |-   |-   |Ja   |
|Gesetzliche Aufbewahrungspflicht|-   |-   |-   |Ja   |Ja   |
|Compliancesuche in Inhalten|- |- |- |Ja |Ja |
|Überwachung und Berichterstellung|Ja |Ja |Ja |Ja |Ja |
|Bedingter Zugriff* |Ja |Ja |Ja |Ja |Ja |
> [!NOTE]
> \*Für bedingten Zugriff sind zusätzliche Lizenzen erforderlich.


| |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Entscheidungspunkt         |Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Compliance- und Sicherheitsanforderungen zu erfüllen?         |
|![Symbol für „Nächste Schritte“](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Nächste Schritte         |Überprüfen Ihrer Organisation aktuellen Lizenzierung, und vergewissern Sie sich, dass alle Unternehmen für die Einhaltung von Vorschriften und Sicherheit erfüllt.         |

Bevor Sie diese Funktionen aktivieren, müssen Sie sicherstellen, dass Sie auf das Security & Compliance Center im Office 365 Admin Center zugreifen können. Mandantenadministratoren verfügen standardmäßig über Zugriff.

Content-Suche und eDiscovery erfordern keine Aktivierung im Compliance Center & Sicherheit.

<a name="location-of-data-in-teams"></a>Speicherort von Daten in Microsoft Teams
-------------------------

Die Microsoft Teams-Daten befinden sich in der geografischen Region, die Ihrem Office 365-Mandanten zugeordnet ist. Zurzeit unterstützt Teams die Regionen Amerika, EMEA und APAC. 

> [!IMPORTANT]
> Microsoft Teams bietet zurzeit nur für neue Mandanten die Datenspeicherung im Vereinigten Königreich und in Indien an. Ein neuer Mandant wird definiert als ein Mandant, über den sich noch kein einziger Benutzer bei Microsoft Teams angemeldet hat. Vorhandene Mandanten aus dem Vereinigten Königreich und aus Indien bleiben bis zur Ankündigung eines Migrationsplans (voraussichtlich im Jahr 2018) in der Region EMEA bzw. APAC.

Weitere Informationen zur Einführung der Datenspeicherung für Microsoft Teams in Indien und im Vereinigten Königreich finden Sie in Ansuman Acharyas Blogbeitrag zur [Einführung der Datenspeicherung für Microsoft Teams in Indien und zu geplanten weiteren geografischen Regionen](https://go.microsoft.com/fwlink/?linkid=867773).

Wenn Sie wissen möchten, in welcher Region sich die Daten für Ihren Mandanten befinden, wechseln Sie zu [Office 365 Admin Center](https://portal.office.com/adminportal/home) > **Einstellungen** > **Organisationsprofil**. Scrollen Sie nach unten zu **Data location** (Datenspeicherort). 

![Screenshot der Tabelle „Data location“ (Datenspeicherort) einschließlich Microsoft Teams im Office 365 Admin Center](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Datenschutz in Microsoft Teams
--------------------------

Als Kunde von Office 365 sind Sie der Besitzer der Daten und verfügen auch über die vollständige Kontrolle. Microsoft verwendet Ihre Daten ausschließlich für die Bereitstellung des Diensts, den Sie abonniert haben. Als Dienstanbieter scannen wir nicht Ihre E-Mails, Dokumente oder Teams zu Werbezwecken oder nicht dienstbezogenen Zwecken. Microsoft hat keinen Zugriff auf hochgeladene Inhalte. Genau wie bei OneDrive for Business und SharePoint Online bleiben die Kundendaten im Mandanten.

Weitere Informationen zu unserer vertrauen und Sicherheit Auschecken weiterführende Informationen finden Sie im [Office 365-Trust Center](https://go.microsoft.com/fwlink/?linkid=855779). Teams folgt den gleichen Leitlinien und Prinzipien wie das Office 365 Trust Center.
