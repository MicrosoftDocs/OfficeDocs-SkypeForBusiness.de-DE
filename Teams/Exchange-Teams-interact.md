---
title: Interaktion von Exchange und Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Lernen Sie die Funktionen kennen, die in Microsoft Teams und den zahlreichen Exchange-Setups gemeinsam verwendet werden, wie zum Beispiel das Erstellen von und die Teilnahme an Teams, das Erstellen von Kanälen usw.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39b60bcd5913619efbf9dfd2aec22813e79921dd
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874895"
---
# <a name="how-exchange-and-microsoft-teams-interact"></a>Interaktion von Exchange und Microsoft Teams

> [!Tip]
> Erfahren Sie in der folgenden Sitzung, wie Teams mit Azure Active Directory (AAD), Microsoft 365-Gruppen, Exchange, SharePoint und OneDrive for Business interagiert: [Microsoft Teams – Grundlagen](https://aka.ms/teams-foundations)

Um den vollen Funktionsumfang von Teams zu nutzen, sollten alle Benutzer für Exchange Online, SharePoint Online und das Erstellen einer Microsoft 365-Gruppe aktiviert sein.

Exchange-Postfächer der Benutzer können online oder lokal gehostet werden.

Benutzer, die auf Exchange Online- oder Exchange-dedizierten vNext gehostet werden, können alle Features von Teams verwenden. Sie können Teams und Kanäle erstellen und diesen beitreten, Besprechungen erstellen und anzeigen, telefonieren und chatten, Benutzerprofilbilder ändern (wenn die Outlook im Web-Postfachrichtlinie diese zulässt) sowie Connectors, Registerkarten und Bots hinzufügen und konfigurieren. Eine umfassendere Liste der verfügbaren Features finden Sie in der Tabelle unten.

In Exchange Online Dedicated (Legacy) gehostete Benutzer müssen mit Azure Active Directory für Microsoft 365 oder Office 365 synchronisiert werden. Sie können Teams und Kanäle erstellen oder diesen beitreten, Registerkarten und Bots hinzufügen und konfigurieren sowie die Chat- und Anruffunktionen nutzen. Sie können jedoch keine Profil Bilder ändern, Besprechungen verwalten, auf Outlook-Kontakte zugreifen oder Connectors verwalten.

> [!IMPORTANT]
> Für die Integration mit einer lokalen Umgebung wird dringend empfohlen, dass Sie eine vollständige klassische Exchange-Hybridbereitstellung mit Exchange Server 2016 oder höher verwenden. Die moderne Hybridunterstützung ist auf Frei/Gebucht beschränkt und bietet z. B. keine Kalenderintegration von Teams in lokale Postfächer. Weitere Informationen zum Einrichten einer Hybridbereitstellung finden Sie unter [Exchange Server-Hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid).

Benutzer mit lokalen Postfächern müssen mit Azure Active Directory synchronisiert werden. Sie können alle Features des oben beschriebenen Szenarios nutzen, aber zusätzlich können sie Besprechungen verwalten, wenn die im Abschnitt [Anforderungen für lokal gehostete Postfächer](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) aufgeführten Anforderungen erfüllt sind.

Die folgende Tabelle enthält eine hilfreiche Kurzübersicht über die Verfügbarkeit von Funktionen auf Basis der Exchange-Umgebung.

**Unterstützte Aktionen:**

| Benutzerpostfach ist gehostet in:                                        | eDiscovery       | Gesetzliche&nbsp;Aufbewahrungspflicht    | Aufbewahrung  | Team- und Kanalverwaltung | Erstellen und Anzeigen von Besprechungen | Bearbeiten des Benutzerprofilbilds | Anrufliste | Verwalten von Kontakten | Zugriff auf Outlook-Kontakte | Voicemail  | Connectors hinzufügen und konfigurieren | Registerkarten hinzufügen und konfigurieren | Bots hinzufügen und konfigurieren |
|---------------------------------------------------------------------|------------------|--------------------|------------|-----------------------|-----------------------------------|-----------------------------|--------------|-----------------|-------------------------|------------|------------------------------|------------------------|------------------------|
| **Exchange Online**                                                 | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja        | Ja                   | Ja                               | Ja <sup>7</sup>             | Ja          | Ja             | Ja <sup>6</sup>        | Ja        | Ja                          | Ja                    | Ja                    |
| **Exchange Online Dedicated vNext**                                 | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja        | Ja                   | Ja                               | Ja <sup>7</sup>             | Ja          | Ja             | Ja <sup>6</sup>        | Ja        | Ja                          | Ja                    | Ja                    |
| **Exchange Online Dedicated – Vorgängerversion** (Synchronisierung in Azure AD erforderlich)  | Ja <sup>1</sup> | Ja <sup>1,2</sup> | Ja <sup>3</sup> | Ja                   | Nein                                | Nein                          | Ja          | Ja             | Nein                      | Ja <sup>4</sup> | Ja <sup>5</sup>                   | Ja                    | Ja                    |
| **Exchange lokal** (Synchronisierung in Azure AD) | Ja <sup>1</sup> | Ja <sup>1</sup>   | Ja <sup>3</sup> | Ja                   | Ja <sup>8</sup>         | Nein                          | Ja          | Ja             | Nein                      | Ja <sup>4</sup> | Ja <sup>5</sup>                   | Ja                    | Ja                    |

<sup>1</sup> Bei allen Hostingoptionen wird eDiscovery unterstützt und die gesetzliche Aufbewahrungspflicht eingehalten.

<sup>2</sup> Die gesetzliche Aufbewahrungspflicht wird bei privaten Chatnachrichten in Teams derzeit noch nicht unterstützt.

<sup>3</sup> Die Aufbewahrung erfolgt in einem Schattenpostfach, in dem die Nachrichten des Online-Benutzers gespeichert werden.

<sup>4</sup> Teams-Benutzer mit lokalen Exchange-Postfächern können Voicemail mit Teams verwenden und Voicemail-Nachrichten in Outlook erhalten, aber Voicemail-Nachrichten können im Team-Client nicht angezeigt oder wiedergegeben werden.

<sup>5</sup> Wenn einer der Besitzer eines Teams Connectors hinzufügen kann, sind alle anderen Personen in diesem Team ebenso in der Lage dazu – auch dann, wenn ihre Postfächer lokal verwaltet sind.

<sup>6</sup> Nur Kontakte im Standardkontaktordner. Der Zugriff auf andere Kontaktordner oder Unterordner wird nicht unterstützt.

<sup>7</sup> Teams berücksichtigt die Einstellung der [Outlook im Web-Postfachrichtlinie](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy), die von Mandantenadministratoren konfiguriert wird, um zu steuern, ob Benutzer Ihr Profilbild ändern können. Wenn die Einstellung **-SetPhotoEnabled** in der Richtlinie deaktiviert ist, können Benutzer ihr Profilbild nicht hinzufügen, ändern oder entfernen, sodass das Porfilebild nicht mit Teams synchronisiert wird, wenn der Administrator das Foto ändert.
<sup>8</sup> Sie müssen die Anforderungen erfüllen, die im Abschnitt [Anforderungen für das Erstellen und Anzeigen von Besprechungen für lokal gehostete Postfächer](#requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises) aufgeführt sind.

## <a name="requirements-to-get-the-most-out-of-microsoft-teams"></a>Voraussetzungen für die optimale Nutzung von Microsoft Teams

Microsoft Teams arbeitet mit mehreren Microsoft 365 und Office 365-Diensten zusammen, um den Benutzern eine umfangreiche Umgebung zu bieten. Zur Unterstützung dieser Erfahrung müssen Sie bestimmte Features oder Dienste aktivieren und Lizenzen zuweisen.

- Den Benutzern muss eine Exchange Online-Lizenz zugewiesen werden.

- SharePoint Online ist erforderlich, um Dateien in Team-Unterhaltungen zu teilen und zu speichern. Microsoft Teams unterstützt die lokale SharePoint-Installation nicht.

- Benutzern muss eine SharePoint Online-Lizenz zugewiesen werden, wenn sie Dateien in Chats teilen möchten. Wenn Benutzer nicht mit SharePoint Online-Lizenzen ausgestattet und diese aktiviert sind, verfügen sie nicht über einen OneDrive for Business-Speicher in Microsoft 365 oder Office 365. Die Dateifreigabe ist in Kanälen weiterhin möglich, ohne OneDrive for Business-Speicher in Microsoft 365 oder Office 365 können die Benutzer jedoch keine Dateien in Chats freigeben.

- Benutzer müssen für die Erstellung von Microsoft 365-Gruppen in Microsoft Teams aktiviert sein.

  > [!IMPORTANT]
  > Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **TeamsOnly**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps möglicherweise nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Um dieses Problem zu beheben, wählen Sie Ihr Profilbild in der oberen rechten Ecke von Microsoft Teams und dann **Einstellungen** aus. Wählen Sie auf der Registerkarte **Allgemein** unter **Anwendung** die Option **Teams als Chat-App für Office registrieren (erfordert einen Neustart der Office-Anwendungen)** aus. Nachdem Sie diese Option ausgewählt haben, schließen Sie alle Office-Apps, einschließlich Outlook, und öffnen Sie sie erneut. Nachdem Sie Outlook geöffnet haben, sind die Anwesenheitsinformationen verfügbar.

## <a name="requirements-to-create-and-view-meetings-for-mailboxes-hosted-on-premises"></a>Anforderungen zum Erstellen und Anzeigen von Besprechungen für lokal gehostete Postfächer

Wenn Postfächer lokal gehostet werden, müssen zum Erstellen und Anzeigen von Besprechungen die folgenden Anforderungen erfüllt sein:

- Für den mit Azure Active Directory synchronisierten Benutzer muss die erforderliche Teams-Lizenz zugewiesen werden.

- Benutzer müssen mit Azure Active Directory synchronisiert werden. Informationen zur Verwendung von Azure AD Connect zwecks Synchronisierung mit Azure Active Directory finden Sie unter [Dokumentation zur Hybrididentität](https://docs.microsoft.com/azure/active-directory/hybrid/).

- Postfächer werden in Exchange Server 2016, kumulatives Update 3 oder höher, gehostet.

- AutoErmittlung und Exchange-Webdienste werden extern veröffentlicht.

- Die OAuth-Authentifizierung wird vorzugsweise über den Exchange-Hybridkonfigurations-Assistenten mit einer vollständigen Hybridkonfiguration (klassisch oder modern) konfiguriert. Wenn Sie den Hybridkonfigurations-Assistenten nicht verwenden können, konfigurieren Sie OAuth wie in [Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) beschrieben.

  > [!NOTE]
  > Exchange vertraut dem OAuth-Token des Teams-Diensts, der als EvoSTS bekannt ist. Schritt 1 sollte ausreichen, aber nur EvoSTS; ACS wird für die Frei/Gebucht-Suche im Kalender verwendet.

- Das Kontrollkästchen für das Feature „Exchange-Hybridbereitstellung“ in Azure AD Connect ist aktiviert.

- Für die Unterstützung der Kalender-App und für das Teams Outlook Add-In für Mac müssen Exchange-Webdienste-URLs als SPNs in Azure AD auf dem Mandanten für den Exchange-Dienstprinzipal konfiguriert werden. Dieser Schritt wird mit dem Hybridkonfigurations-Assistenten oder den folgenden [manuellen Schritten für die moderne Hybridauthentifizierung](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication#add-on-premises-web-service-urls-as-spns-in-azure-ad) ausgeführt.

So aktivieren Sie die Kalenderdelegation für diese Benutzer

- Sie müssen auch die Schritte 2–3 ausführen, wie in [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) beschrieben. Diese Schritte erteilen der Teams-Planungsanwendung die erforderlichen Berechtigungen, um die Delegiertenberechtigungen zu bestätigen.
 
  > [!NOTE]
  > Schritt 2 umfasst die Rollenzuweisung für ArchiveApplication, die für die Delegation nicht erforderlich ist.

- Das Teams-Terminplanungs-Add-In für Outlook benötigt zur Planung einer Besprechung im Auftrag einer anderen Person Exchange 2013 CU19 oder höher. Dies dient zur Unterstützung der nicht authentifizierten Erkennung des Postfachs durch unseren Dienst, um die Berechtigungen der Stellvertretung anhand des Delegatorpostfachs zu überprüfen. Die Standorte von Stellvertretung und Delegator können Exchange 2013 oder höher oder Exchange Online sein, aber die AutoErmittlung muss zu Exchange 2013 CU19 oder höher auflösen.

## <a name="additional-considerations"></a>Zusätzliche Überlegungen

Hier sind einige weitere Punkte, die Sie berücksichtigen sollten, wenn Sie Microsoft Teams in Ihrer Organisation implementieren.

- In Microsoft Teams funktionieren Sicherheits- und Compliance-Funktionen wie eDiscovery, Inhaltssuche, Archivierung und gesetzliche Aufbewahrungspflicht am besten in Exchange Online- und SharePoint Online-Umgebungen. Für Kanalunterhalten werden Nachrichten im Gruppenpostfach in Exchange Online als Journal erfasst und stehen für eDiscovery zur Verfügung. Bei Aktivierung von SharePoint Online und OneDrive for Business (mit Geschäfts- oder Schulkonto) für Benutzer in der gesamten Organisation stehen diese Compliance-Funktionen auch für alle Dateien innerhalb von Teams zur Verfügung.

- Sie können die Konfiguration von Konformitätsrichtlinien in Teams und Exchange mithilfe des bedingten Zugriffs Steuern und schützen. Weitere Informationen finden Sie unter [Wie funktionieren Richtlinien für bedingten Zugriff in Verbindung mit Microsoft Teams?](security-compliance-overview.md#how-conditional-access-policies-work-for-teams)

- Wenn Ihre Organisation Compliance-Anforderungen erfüllen muss, um sicherzustellen, dass alle Besprechungsdiskussionen gefunden werden können, sollten Sie private Besprechungen deaktivieren, wenn der Organisator über ein lokales Exchange-Postfach verfügt. Weitere Informationen finden Sie unter [Zulassen der Planung privater Besprechungen](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#allow-scheduling-private-meetings).

- Bei einer Hybridbereitstellung von Exchange sind Inhalte aus Chatnachrichten unabhängig davon durchsuchbar, ob Chatteilnehmer über ein cloudbasiertes oder ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Durchsuchen von cloudbasierten Postfächern für lokale Benutzer](https://docs.microsoft.com/office365/securitycompliance/search-cloud-based-mailboxes-for-on-premises-users). Weitere Informationen zur Suche nach Inhalten in Teams finden Sie unter [Ausführen einer Inhaltssuche im Microsoft 365 Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search#searching-microsoft-teams-and-office-365-groups).

- Für den Anwesenheitsstatus muss Microsoft Teams prüfen, ob das Postfach auf Exchange Online oder lokal gehostet wird. Der Dienst entscheidet dann, von wo aus auf die Mailbox zugegriffen wird. Damit der Teams-Dienst den Postfachstandort über den REST-API-Aufruf an den Exchange Online-Dienst überprüfen kann, müssen Sie eine Exchange-Hybridumgebung bereitstellen, indem Sie den Exchange-Hybridkonfigurations-Assistenten ausführen, wie in [Erstellen einer Hybridbereitstellung mit dem Hybridkonfigurations-Assistenten](https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid) beschrieben.

## <a name="troubleshooting"></a>Problembehandlung

Eine vollständige Problembehandlungsanleitung zu diesem Thema finden Sie unter [Beheben von Interaktionsproblemen zwischen Microsoft Teams und Exchange Server](https://docs.microsoft.com/microsoftteams/troubleshoot/known-issues/teams-exchange-interaction-issue).
