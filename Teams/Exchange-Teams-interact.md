---
title: Interaktion von Exchange und Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: "Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7da92ce791349994474c76fe736a06ddcd67999
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
<a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams 
=========================================

Um den vollen Funktionsumfang von Microsoft Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Office 365-Gruppe aktiviert sein.

Die Exchange-Postfächer der Benutzer können online oder lokal gehostet werden. In Exchange Online oder Exchange Dedicated vNext gehostete Benutzer können alle Funktionen von Microsoft Teams verwenden. Sie können Teams und Kanäle erstellen und diesen beitreten, Besprechungen erstellen und anzeigen, anrufen und chatten, Benutzerprofilbilder ändern sowie Connectors, Registerkarten und Bots hinzufügen und konfigurieren.

In Exchange Online Dedicated – Legacy oder Exchange lokal gehostete Benutzer müssen mit Azure Active Directory für Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen oder an diesen teilnehmen, Registerkarten und Bots hinzufügen und konfigurieren sowie chatten und anrufen. Sie können jedoch keine Benutzerprofilbilder ändern oder Connectors hinzufügen und konfigurieren. Sie können Nachrichten von Connectors empfangen, die von anderen Benutzern konfiguriert wurden. Die Möglichkeiten zum Erstellen und Anzeigen von Besprechungen hängen von der Version ab: Das Erstellen und Anzeigen von Besprechungen wird für das kumulative Update 3 (CU3) von Exchange 2016 und höher unterstützt, aber nicht für niedrigere Versionen.

Die folgende Tabelle enthält Informationen für Benutzer, für die Exchange Online in verschiedenen Umgebungen gehostet ist.

**Unterstützte Aktionen:** 

| Benutzerpostfach ist gehostet in:   | Teams erstellen   |An Teams teilnehmen|Kanäle erstellen|Besprechungen erstellen und anzeigen|Benutzerprofilbild bearbeiten|Connectors hinzufügen und konfigurieren|Registerkarten hinzufügen und konfigurieren|Bots hinzufügen und konfigurieren|
|---|---|---|---|---|---|---|---|---|
|**Exchange Online**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated vNext**|Ja|Ja|Ja|Ja|Ja|Ja|Ja|Ja|
|**Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)|Ja|Ja|Ja|Nein|Nein|Nein|Ja| Ja|
|**Exchange lokal** (Synchronisierung in Azure AD erforderlich)|Ja|Ja|Ja|Ja*|Nein|Nein|Ja|Ja|
                                                            
*\*Exchange 2016 CU3 und höher unterstützt*

Weitere Informationen:

-   Microsoft Teams unterstützt keine lokalen SharePoint-Instanzen.

-   SharePoint Online ist erforderlich, um Dateien in Teamunterhaltungen freizugeben und zu speichern.

-   OneDrive for Business ist erforderlich, um Dateien in privaten Chats freizugeben und zu speichern.

-   Wenn Benutzern keine SharePoint Online-Lizenzen zugewiesen sind, verfügen Sie über keinen OneDrive for Business-Speicher in Office 365. Die Dateifreigabe funktioniert weiterhin in Kanälen, die Benutzer können jedoch ohne OneDrive for Business-Speicher in Office 365 keine Dateien in Chats freigeben.

-   Benutzer müssen für die Erstellung von Office 365-Gruppen in Microsoft Teams aktiviert sein.

-   In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

**Wichtig:** Benutzer, die an Unterhaltungen teilnehmen, die in der Chatliste in Microsoft Teams enthalten sind, müssen über ein (cloudbasiertes) Exchange Online-Postfach verfügen, damit Administratoren Chatunterhaltungen durchsuchen können. Das liegt daran, dass Unterhaltungen, die in der Chatliste enthalten sind, in den cloudbasierten Postfächern der Chatteilnehmer gespeichert werden. Wenn Chatteilnehmer kein Exchange Online-Postfach haben, können Administratoren die Chatunterhaltungen nicht durchsuchen oder im In-Situ-Speicher ablegen. In einer hybriden Exchange-Bereitstellung zum Beispiel können Benutzer mit lokalen Postfächern möglicherweise an Unterhaltungen teilnehmen, die Teil der Chatliste in Microsoft Teams sind. In diesem Fall kann der Inhalt dieser Unterhaltungen jedoch nicht durchsucht und nicht im In-Situ-Speicher abgelegt werden, da die Benutzer nicht über cloudbasierte Postfächer verfügen. Weitere Details zur Inhaltssuche und zu Microsoft Teams finden Sie unter [Ausführen einer Inhaltssuche im Office 365 Security & Compliance Center](https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a).

**Tipp:**   Informationen zur Verwendung von Azure AD Connect zwecks Synchronisierung mit Azure Active Directory finden Sie unter [*Integrieren Ihrer lokalen Identitäten mit Azure Active Directory*](https://go.microsoft.com/fwlink/?linkid=854600).
