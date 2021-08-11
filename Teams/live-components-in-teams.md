---
title: Verwalten von Livekomponenten in Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Livekomponenten in Teams verwalten.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb472822f7d55636bfd5ee4c48e7c962a705f6e05fd65b263952895040d69f7c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305017"
---
# <a name="manage-live-components-in-teams"></a>Verwalten von Livekomponenten in Teams

Live-Komponenten in Teams Chat bieten eine neue Möglichkeit, gemeinsam Ideen zu entwickeln, zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente , z. B. eine Tabelle, eine Aufgabenliste oder einen Absatz, in der jeder in Ihrem Chat inline bearbeiten und Änderungen sehen kann, während er vorgenommen wurde. Dies bedeutet, dass Sie Ideen und Feedback von Ihrem Team sammeln können, während Sie weniger Besprechungen abhalten und die Notwendigkeit langer Chatthreads minimieren.

**Aufgaben schneller gemeinsam erledigen.** Quelldaten einer Agenda, Nachverfolgen der Aktionselemente einer Gruppe oder gemeinsame Notizen. Dies sind nur einige Szenarien, die mit Livekomponenten einfacher gemacht werden.

**Teilen von Komponenten.** In dieser Version können Sie Livekomponenten in verschiedenen Teams Chats freigeben. Empfänger können von überall aus bearbeiten und Updates sofort anzeigen, unabhängig davon, wo die Änderungen vorgenommen wurden. In zukünftigen Versionen werden Livekomponenten in Teams Besprechungsnotizen und -kanälen, Outlook und schließlich in allen Microsoft 365-Anwendungen unterstützt.

**Beginnen Sie mit dem Chat, erstellen Sie von dort aus.** Jede Komponente, die Sie aus Teams Chat erstellen, wird automatisch in einer Datei in OneDrive gespeichert. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei wechseln, wo Sie über einen größeren visuellen Platz für die Bearbeitung verfügen und beliebig viele Komponenten hinzufügen können.

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar unter Teams Apps unter Windows, Mac, Linux, iOS und Android.

Ab Anfang September werden Livekomponenten global verfügbar sein. Ende September ist es für Government Community Cloud Mod (GCC) verfügbar.

## <a name="settings-management"></a>Einstellungen verwaltung

Live-Komponenten werden mit Microsoft Fluid Framework erstellt, die in Microsoft 365 Suite unterstützt werden und über SharePoint Online und nicht über das Teams Admin Center gesteuert werden.

Sie benötigen die neueste Version von [SharePoint Online-PowerShell-Modul,](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) um alle Fluid Experiences in Ihrem Office 365 Mandanten zu aktivieren oder zu deaktivieren. Microsoft Fluid Framework ist standardmäßig für alle Zielversionsmandanten **aktiviert.** Da Live-Komponenten für die Zusammenarbeit konzipiert sind, werden die Komponenten immer als bearbeitbar für andere personen freigegeben, auch wenn Ihr Mandant auf "Schreibgeschützt" für andere Dateitypen festgelegt ist. Weitere Informationen finden Sie unter dem Link **"Weitere Informationen"** neben der Einstellung.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Überprüfen, ob die Fluid Framework über das SharePoint Online-PowerShell-Cmdlet aktiviert ist

1. [Verbinden zu SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Überprüfen Sie, ob Fluid Framework aktiviert ist, indem Sie das Cmdlet Get-SPOTenant ohne Argumente ausführen.

3. Stellen Sie sicher, dass der Wert von IsFluidEnabled **"true"** ist.

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Aktivieren der Fluid Framework über das SharePoint Online-PowerShell-Cmdlet 

1. [Verbinden zu SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Aktivieren von Fluid mithilfe des Cmdlets Set-SPOTenant -IsFluidEnabled $true 
   
   Die Änderung nimmt eine kurze Zeit in Anspruch, bis sie in Ihrem Mandanten angewendet wird. 

Das Feature wird auf Teams Windows Desktop, Mac, iOS, Android verfügbar sein. Wenn diese Option aktiviert ist, wird benutzern eine neue Option zum Einfügen von Livekomponenten in die Nachrichtenerstellungsoberfläche für diese Clients angezeigt.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Deaktivieren von Fluid Framework über SharePoint Online-PowerShell-Cmdlet

1. [Verbinden zu SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Deaktivieren Sie Fluid mithilfe des Cmdlets Set-SPOTenant -IsFluidEnabled $false Set-SPOTenant. 

   Die Änderung nimmt eine kurze Zeit in Anspruch, bis sie in Ihrem Mandanten angewendet wird. 

Wenn Sie diese Funktion erneut aktivieren müssen, können Sie SharePoint Online-PowerShell-Cmdlets verwenden.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Das Erstellen einer Tabelle oder Aufgabenliste als erste Komponente nach dem Neustart der Teams-App kann etwas mehr Zeit in Anspruch nehmen.

- Andere Chatmitglieder erhalten eine E-Mail-Benachrichtigung, wenn sie mit einem @-Symbol erwähnt werden. (Erwähnt Benachrichtigungen im Teams Aktivitätsfeed werden in Kürze verfügbar sein.)

- Die Suche nach Livekomponenten innerhalb Teams Suche gibt einen Link zu der Komponente in office.com zurück, nicht zur Chatnachricht selbst.

- Live-Komponenten sind in Verbundchats deaktiviert und für reguläre Chats mit einem Gastkonto mit Azure B2B aktiviert.

- Während Sie eine Komponente in Teams Kanälen und anderen Microsoft 365-Apps freigeben können, erhalten Empfänger derzeit an den meisten Stellen einen Link. Die Inlinebearbeitung ist für weitere Benutzeroberflächen in der Zukunft geplant.

## <a name="storage-of-fluid-files"></a>Storage von `.fluid` Dateien

**Wie `.fluid` werden gespeichert?**

In Teams erstellte Livekomponenten werden durch eine Datei gesichert, `.fluid` die im OneDrive for Business des Erstellers gespeichert ist. Eine Datei in OneDrive for Business bedeutet, dass Benutzer Livekomponenten (Dateien) so einfach erstellen, ermitteln und verwalten können `.fluid` wie jedes Office Dokument.

Benutzer können in `.fluid` Dateien von Office.com und OneDrive for Business nach Inhalten suchen.
`.fluid` Dateien funktionieren mit Datengovernance-Features wie eDiscovery, Überwachung, Berichterstellung und gesetzliche Aufbewahrungspflicht.

`.fluid`Dateien werden nun auf Office.com und OneDrive for Business angezeigt, z. B. in den Bereichen "Zuletzt verwendet" und "Empfohlen".
`.fluid`Dateien können in früheren Versionen von OneDrive for Business wiederhergestellt werden.

Chatteilnehmer müssen über ein OneDrive Konto verfügen, um Livekomponenten zu erstellen. Ohne ein gültiges OneDrive Konto können Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern erstellt wurde, die über ein gültiges OneDrive Konto verfügen, aber kein eigenes erstellen können.

[Das Verschieben](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) einer `.fluid` Datei von OneDrive zu einer SharePoint Website führt dazu, dass die Livekomponente in Teams Chat nicht geladen werden kann.

**Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?**

[OneDrive Aufbewahrungsrichtlinien](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) gelten `.fluid` für Dateien genauso wie für andere vom Benutzer erstellte Inhalte.

**Wie werden `.fluid` Dateien freigegeben?**

Live-Komponenten können in Teams Chat eingefügt oder von einem Chat in einen anderen kopiert werden. (Live-Komponenten werden in Kanälen noch nicht unterstützt.) Sie sind standardmäßig auf die vorhandenen Berechtigungen des Mandanten festgelegt, aber Benutzer können berechtigungen vor dem Senden ändern, um sicherzustellen, dass jeder Zugriff hat.

Das Öffnen von Komponenten aus Teams Chat in Office.com bietet am oberen Rand des Fensters Freigabefunktionen, ähnlich den Freigabeoptionen, die für andere Office Dokumente angeboten werden.

**Was geschieht, wenn eine `.fluid` Datei beschädigt oder beschädigt wird?**

Mit dem Versionsverlauf können Sie frühere Versionen der Datei überprüfen und kopieren.

**Welche Apps können Dateien öffnen und `.fluid` bearbeiten?**

`.fluid`Dateien können nur als Links in Ihrem Browser geöffnet werden, z. B. Office.com, und als Livekomponenten in Teams Chat. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder in OneDrive for Business oder SharePoint Online hochzuladen.
