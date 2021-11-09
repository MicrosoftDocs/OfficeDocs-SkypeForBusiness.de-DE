---
title: Verwalten von Livekomponenten in Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie Livekomponenten in Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6be8db0fdde7509f5721277b4ee631f7a814171d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830219"
---
# <a name="manage-live-components-in-teams"></a>Verwalten von Livekomponenten in Teams

Livekomponenten in Teams bieten eine neue Möglichkeit, gemeinsam Ideen zu erstellen und Entscheidungen zu treffen. Senden Sie eine Komponente , z. B. eine Tabelle, Aufgabenliste oder einen Absatz, in der jeder chat inline bearbeiten und die vorgenommenen Änderungen sehen kann. Dies bedeutet, dass Sie Ideen und Feedback von Ihrem Team sammeln können, während Sie weniger Besprechungen halten und gleichzeitig den Bedarf an langen Chatthreads minimieren.

**Erledigen Sie Aufgaben schneller zusammen.** Sie können eine Tagesordnung aus der Menge stammen lassen, die Aktionselemente einer Gruppe nachverfolgen oder gemeinsam Notizen machen. Dies sind nur einige wenige Szenarien, die mit Livekomponenten einfacher gemacht werden.

**Teilen von Komponenten.** In dieser Version können Sie Livekomponenten in verschiedenen Chats Teams teilen. Empfänger können von überall aus bearbeiten und Aktualisierungen sofort sehen, unabhängig davon, wo die Änderungen vorgenommen wurden. In zukünftigen Versionen werden Livekomponenten in Teams Besprechungsnotizen und -kanälen, Outlook und schließlich in allen Microsoft 365 unterstützt.

**Starten Sie im Chat, erstellen Sie von dort aus.** Jede Komponente, die Sie aus Teams Chat erstellen, wird automatisch in einer Datei in OneDrive. Sie können also mit der Zusammenarbeit im Chat beginnen und später zu der Datei wechseln, in der Sie über einen größeren visuellen Bereich zum Bearbeiten verfügen und so viele Komponenten hinzufügen können, wie Sie möchten.

## <a name="clients-and-platforms"></a>Clients und Plattformen

Verfügbar für Teams-Apps Windows, Mac, Linux, iOS und Android.

Ab Anfang September stehen Livekomponenten global zur Verfügung. Ende September wird es für Government Community Cloud Mod (GCC) verfügbar sein.

## <a name="settings-management"></a>Einstellungen Verwaltung

Live-Komponenten werden mit integrierten Microsoft Fluid Framework in der gesamten Microsoft 365-Suite unterstützt und über SharePoint Online und nicht über das Teams Admin Center gesteuert.

Sie benötigen die neueste Version des [PowerShell SharePoint Online-PowerShell-Moduls,](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) um alle flüssigen Be erfahrungen in Ihrem Mandanten zu aktivieren Office 365 deaktivieren. Microsoft Fluid Framework standardmäßig für alle Mandanten mit Targeted Release auf **EIN** festgelegt. Da Livekomponenten für die Zusammenarbeit entwickelt wurden, werden die Komponenten von anderen Personen immer als bearbeitbar freigegeben, auch wenn Ihr Mandant für andere Dateitypen standardmäßig auf "Nur anzeigen" festgelegt ist. Weitere Details **finden Sie unter** dem Link Weitere Informationen neben der Einstellung.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Überprüfen, ob die Fluid Framework über das PowerShell-Cmdlet "SharePoint Online" aktiviert ist

1. [Verbinden Sie SharePoint Online-PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Überprüfen Sie, Fluid Framework aktiviert ist, indem Sie das Get-SPOTenant-Cmdlet ohne Argumente ausführen.

3. Überprüfen Sie, ob der Wert von IsFluidEnabled wahr **ist.**

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Aktivieren des Fluid Framework über das SharePoint Online-PowerShell-Cmdlet 

1. [Verbinden Sie SharePoint Online-PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Aktivieren von Fluid mithilfe des Cmdlets Set-SPOTenant -IsFluidEnabled-$true 
   
   Die Änderung dauert ein kurzes Zeit, bis sie für alle Ihre Mandanz zur Anwendung kommt. 

Das Feature ist für Teams Windows, Mac, iOS und Android verfügbar. Wenn die Option aktiviert ist, wird den Benutzern eine neue Option zum Einfügen von Livekomponenten in die Erfahrung zum Verfassen von Nachrichten für diese Clients angezeigt.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Deaktivieren von Fluid Framework über SharePoint Online-PowerShell-Cmdlet

1. [Verbinden Sie SharePoint Online-PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Deaktivieren Sie "Fluid" Set-SPOTenant das Set-SPOTenant -IsFluidEnabled-$false. 

   Die Änderung dauert ein kurzes Zeit, bis sie für alle Ihre Mandanz zur Anwendung kommt. 

Wenn Sie diese Funktion erneut aktivieren müssen, können Sie SharePoint PowerShell-Online-Cmdlets verwenden.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Bekannte Einschränkungen

- Das Erstellen einer Tabelle oder Aufgabenliste als erste Komponente nach dem Neustart Teams App kann einige Zeit dauern.

- Andere Chatmitglieder erhalten eine E-Mail-Benachrichtigung, wenn sie mit einem @-Symbol erwähnt werden. (Benachrichtigungen über At-Erwähnungen im Teams-Aktivitätsfeeds werden in Kürze verfügbar sein.)

- Bei der Suche nach Livekomponenten innerhalb Teams Suche wird ein Link zur Komponente in der office.com und nicht die Chatnachricht selbst angezeigt.

- Livekomponenten sind in Partnerchats deaktiviert und für normale Chats mit einem Gastkonto aktiviert, das Azure B2B verwendet.

- Zwar können Sie eine Komponente in Teams Kanälen und anderen Microsoft 365-Apps freigeben, die Empfänger erhalten derzeit an den meisten Stellen jedoch einen Link. Die Inlinebearbeitung ist in Zukunft für weitere Erfahrungen geplant.

## <a name="storage-of-fluid-files"></a>Storage von `.fluid` Dateien

**Wie `.fluid` werden gespeichert?**

In einem -Teams erstellte Livekomponenten werden von einer Datei unterstützt, die in der Datei `.fluid` des Erstellers OneDrive for Business. Als Datei in OneDrive for Business bedeutet dies, dass Benutzer Livekomponenten (Dateien) genauso einfach erstellen, entdecken und verwalten können wie `.fluid` jedes Office Dokument.

Benutzer können über `.fluid` "Office.com" und "OneDrive for Business" nach Inhalten in Dateien OneDrive for Business.
`.fluid` Dateien funktionieren mit Daten-Governance-Features wie eDiscovery, Überwachung, Berichterstellung und gesetzliche Erkung.

`.fluid`Dateien werden jetzt auf Office.com und OneDrive for Business angezeigt, z. B. in den Bereichen Zuletzt verwendet und Empfohlen.
`.fluid`Dateien können in früheren Versionen von ihrem OneDrive for Business.

Chatteilnehmer müssen über ein OneDrive verfügen, um Livekomponenten erstellen zu können. Ohne ein gültiges OneDrive-Konto können die Chatteilnehmer möglicherweise weiterhin an einer Komponente zusammenarbeiten, die von anderen Benutzern erstellt wurde, die über ein gültiges OneDrive-Konto verfügen, aber keine eigene Komponente erstellen können.

[Das](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) Verschieben einer Datei von OneDrive auf eine SharePoint-Website führt dazu, dass die Livekomponente `.fluid` im Chat Teams wird.

**Was geschieht, wenn der Besitzer der Datei das Unternehmen verlässt?**

[OneDrive Aufbewahrungsrichtlinien](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) gelten für Dateien genauso wie für andere vom Benutzer erstellte `.fluid` Inhalte.

**Wie werden `.fluid` Dateien freigegeben?**

Livekomponenten können in einem Chat Teams eingefügt oder aus einem Chat in einen anderen kopiert werden. (Livekomponenten werden in Kanälen noch nicht unterstützt.) Sie werden standardmäßig auf die vorhandenen Berechtigungen des Mandanten festgelegt, aber benutzer können vor dem Senden Berechtigungen ändern, um sicherzustellen, dass jeder Zugriff hat.

Das Öffnen von Komponenten Teams Chats in Office.com bietet am oberen Rand des Fensters Freigabefunktionen, ähnlich wie die Freigabeoptionen, die für andere Office werden.

**Was `.fluid` passiert, wenn eine Datei beschädigt oder beschädigt wird?**

Der Versionsverlauf ermöglicht es Ihnen, frühere Versionen der Datei zu überprüfen und zu kopieren.

**Welche Apps können Dateien öffnen und `.fluid` bearbeiten?**

`.fluid`Dateien können nur als Links in Ihrem Browser, z. B. Office.com, und als Livekomponenten in Teams geöffnet werden. Wenn sie heruntergeladen werden, können sie nicht erneut geöffnet werden, ohne sie zuerst wieder in den OneDrive for Business oder SharePoint Online hochzuladen.
