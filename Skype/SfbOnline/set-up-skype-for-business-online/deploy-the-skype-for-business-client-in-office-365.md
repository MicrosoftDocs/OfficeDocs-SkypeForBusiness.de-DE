---
title: Bereitstellen des Skype for Business-Clients in Microsoft 365 AOR Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Erfahren Sie, wie Sie Skype for Business in kleinen, mittleren und großen Organisationen planen und bereitstellen und für Ihre Benutzer verfügbar machen. '
ms.openlocfilehash: d7c310935c5fa97873183d18b264616404471895
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777240"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365

In diesem Artikel werden die Optionen erläutert, wie Sie, der **[Administrator](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)**, die Skype for Business-App für die Personen in Ihrer Organisation bereitstellen können.
  
Bevor Sie Skype for Business für Ihre Benutzer bereitstellen, stellen Sie sicher, dass Sie die Schritte 1-3 im Artikel [Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)ausgeführt haben. Auf diese Weise wird Skype for Business für Ihre Domäne eingerichtet, jeder Benutzer erhält eine Lizenz und Sie haben Chats sowie[Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md) für Ihre Organisation konfiguriert.
  
> [!NOTE]
> Benutzer, die die Skype for Business-App installieren möchten, müssen lokale Administratoren ihres PCs oder Geräts sein. Alternativ können sie auch Mitglieder einer lokalen Gruppe sein, die über die Berechtigung zum Installieren von Anwendungen auf ihrem PC oder Gerät verfügt. Wenn Ihre Benutzer nicht berechtigt sind, Software auf Ihren Geräten zu installieren, müssen Sie die Skype for Business-App für Sie installieren. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Für die meisten kleinen und mittleren Unternehmen

 **Schrittweise Installationsanleitung**: Wenn Sie ein kleines oder mittleres Unternehmen haben, empfehlen wir, die Benutzer einfach zu bitten, die Skype for Business-App auf ihrem PC zu installieren. Verweisen Sie auf diese Anweisungen: [Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Wenn sie einen Mac verwenden, verweisen Sie sie auf [Einrichten von Skype for Business (Lync) für Mac 2011 für Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). Die Skype for Business-App wird getrennt von den anderen Office-Apps installiert.
  
 **Microsoft 365-Apps für Unternehmenskunden:** Wenn in Ihrem Unternehmen ein Office 365-Plan mit Microsoft 365-Apps für Unternehmen wie dem E3-Plan verwendet wird, wird die Skype for Business-App zur gleichen Zeit installiert, in der die Benutzer Word, Excel, PowerPoint usw. herunterladen und installieren. Das bedeutet auch, dass Sie Skype for Business nur deinstallieren können, wenn Sie alle Office-Installation deinstallieren.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Wählen, ob Skype for Business für Ihre Benutzer zur Verfügung stehen soll

Als [Administrator](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) können Sie auswählen, ob Sie die Skype for Business-App für Ihre Benutzer verfügbar machen möchten.
  
- **So steuern Sie, ob jeder in Ihrem Unternehmen die Software erhält**: Anmelden beim Microsoft 365 Admin Center, wechseln Sie zu **meine Software installieren**, und wählen Sie dann die Software aus, die für die Benutzer verfügbar sein soll.
    
    ![Wählen Sie die Software aus, die Sie den Personen in Ihrem Unternehmen zur Verfügung stellen möchten.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **So steuern Sie, ob bestimmte Personen in Ihrem Unternehmen die Software erhalten**: Melden Sie sich beim Microsoft 365 Admin Center an, wechseln Sie zu **Benutzer** > **aktive Benutzer**, wählen Sie die Person aus, die Sie Zugriff auf die Software gewähren möchten, und klicken Sie dann neben **Produktlizenzen** auf **Bearbeiten** , und aktivieren oder deaktivieren Sie die Lizenz.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Wenn Sie sehen möchten, welche Pläne den Personen in Ihrer Organisation zugewiesen sind, müssen Sie sich beim Microsoft 365 Admin Center anmelden, > **Benutzer** > **aktive**Benutzer. Wählen Sie die Person in der Liste aus, und schauen Sie unter **Produktlizenzen**nach. Wenn Sie das klassische Admin Center verwenden, suchen Sie unter **zugewiesene Lizenz**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Manuelle Bereitstellung von Skype for Business für Ihre Benutzer
<a name="bkmk_manual_1"> </a>

Wenn Sie möchten, dass Ihre Benutzer die Skype for Business-APP von einem Speicherort in Ihrem Netzwerk anstatt aus dem Internet installieren, können Sie die Setupdateien herunterladen. Gehen Sie dazu im Abschnitt **Benutzer Software manuell bereitstellen** des Microsoft 365 admin Centers. Anschließend können Sie die Datei "Setup. exe" **Installieren** und an einem Netzwerkspeicherort speichern.
  
Sie haben auch die Möglichkeit, die Skype for Business Basic-App für die Benutzer herunterzuladen. Sie können [Microsoft Skype for Business Basic (32 oder 64 Bit)](https://www.microsoft.com/download/details.aspx?id=49440)herunterladen.
  
Sowohl für die vollständige als auch für die Basic-Version der Skype for Business-App müssen Sie nach dem Herunterladen der Setupdateien den Netzwerkpfad manuell an die Benutzer senden (zum Beispiel per E-Mail). Dann können sie das Setupprogramm ausführen, um die App auf ihrem Computer zu installieren.
  
Sie können diese Downloads auch zum Bereitstellen der Skype for Business-App für Ihre Benutzer mithilfe Ihrer vorhandenen Softwarebereitstellungstools und -prozesse verwenden.
  
## <a name="for-larger-and-enterprise-organizations"></a>Für größere und sehr große Unternehmen

> [!NOTE]
> Dieser Abschnitt betrifft nur die in Office 365-Plänen verfügbare Skype for Business-App. Wenn Ihre Organisation eine volumenlizenzierte Version der Skype for Business-app (Windows Installer-basiert (MSI)) verwendet, lesen Sie [Anpassen der Windows-Clientinstallation in Skype for Business Server](https://technet.microsoft.com/library/jj204934.aspx).
  
In vielen Großunternehmen haben Benutzer nicht die Berechtigung zum Installieren von Software auf ihren Computern. Stattdessen wird die Software von den IT-Abteilungen auf den Computern bereitgestellt. IT-Abteilungen möchten unter Umständen auch die in der Organisation verwendete Internet- oder Netzwerkbandbreite steuern und Software daher von einem Speicherort im lokalen Netzwerk aus statt über das Internet oder das Unternehmensnetzwerk installieren.
  
Mit Office 365 haben Sie verschiedene Möglichkeiten, die Skype for Business-App bereitzustellen, wenn Sie steuern möchten, von wo aus Sie installiert werden soll. Zu den folgenden Optionen gehören:
  
- Laden Sie die Skype for Business-App aus dem Microsoft 365 Admin Center in Ihr lokales Netzwerk herunter, wie in [Manuelle Bereitstellung von Skype for Business für Ihre Benutzer](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)beschrieben.
    
- Verwenden Sie das **[Office-Bereitstellungs Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** , um entweder Microsoft 365-Apps für Unternehmen oder die Skype for Business-app in Ihr lokales Netzwerk herunterzuladen. Verwenden Sie das Office-Bereitstellungstool anschließend zum Bereitstellen der App für Ihre Benutzer. Mit dem Office-Bereitstellungstool können Sie unterschiedliche Aspekte der Bereitstellung festlegen, wie etwa Sprachen oder Version (32 Bit oder 64 Bit).
    
- Verwenden Sie Ihre vorhandenen Softwarebereitstellungstools und-Prozesse wie Microsoft Endpoint Configuration Manager, um Microsoft 365-Apps für Unternehmen oder die Skype for Business-App für Ihre Benutzer bereitzustellen. Sie können Ihre vorhandenen Tools und Prozesse mit dem [Office-Bereitstellungs Tool](https://go.microsoft.com/fwlink/p/?LinkID=626065) oder mit der Software verwenden, die Sie aus dem Microsoft 365 Admin Center heruntergeladen haben.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Zusätzliche Informationen zur Verwendung des Office-Bereitstellungstools

Details zum Herunterladen des Office-Bereitstellungstools und weitere Informationen zum Installieren der Skype for Business-APP und anderer Office 365-Client-apps finden Sie unter [Verwalten von Software Downloadeinstellungen in Office 365](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Im folgenden finden Sie eine Übersicht über die Schritte, die bei der Verwendung des Office-Bereitstellungstools zum Bereitstelleneiner App erforderlich sind:
  
1. **[Laden Sie die aktuellste Version des Office-Bereitstellungstools](https://www.microsoft.com/download/details.aspx?id=49117)** aus dem Microsoft Download Center herunter.
    
2. Erstellen Sie die configuration.xml-Datei zur Verwendung mit dem Office-Bereitstellungstool mit den von Ihnen gewünschten Client-App-Einstellungen, wie zum Beispiel der Version (32-Bit oder 64-Bit), der Installationssprache usw.
    
3. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Setupdateien vom Office Content Delivery Network (CDN) in Ihr lokales oder internes Netzwerk herunterzuladen.
    
4. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Office-Client-Apps einschließlich der Skype for Business-App zu installieren.
    
Details zur Verwendung des Office-Bereitstellungstools und zur configuration.xml-Datei finden Sie hier:
  
- [Office-Bereitstellungstool - Überblick](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml - Einstellungen](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Weitere Informationen zur Verwendung von Microsoft Endpoint Configuration Manager

Sie können Ihre vorhandenen Softwarebereitstellungstools und-Prozesse wie Microsoft Endpoint Configuration Manager zum Bereitstellen der Skype for Business-App verwenden. Sie können diese Tools und Prozesse entweder mit der Software verwenden, die Sie aus dem Microsoft 365 Admin Center oder mit dem Office-Bereitstellungs Tool herunterladen.
  
Weitere Informationen zur Bereitstellung von Software mit Configuration Manager finden Sie in den folgenden Artikeln:
  
- [Erstellen von Anwendungen in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/create-applications)
    
- [Bereitstellen von Anwendungen mit Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
    
Wenn Sie die Skype for Business-App als Teil der Bereitstellung von Microsoft 365-Apps für Unternehmen bereitstellen, lesen Sie [Verwalten von Microsoft 365-Apps für Unternehmen mit Configuration Manager](https://docs.microsoft.com/configmgr/sum/deploy-use/manage-office-365-proplus-updates).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planen von Updates der Skype for Business-App

Im Rahmen der Bereitstellung der Skype for Business-App müssen Sie auch festlegen, wie Updates nach der Installation von Skype for Business durchgeführt werden sollen. Diese Updates können z. B. neue Funktionen, verbesserte Sicherheit oder aber Updates, die Verbesserungen der Stabilität oder Leistung bieten, enthalten. Sie müssen sich dabei folgende zwei Hauptfragen stellen:
  
- Woher möchten Sie die Updates erhalten?
    
- Wie oft möchten Sie Funktionsupdates erhalten?
    
Sie können zwar festlegen, woher Sie die Updates beziehen und wie oft Sie Funktionsupdates erhalten möchten, nicht jedoch, welche konkreten Sicherheitsupdates oder allgemeine Updates Sie erhalten.
  
 **Bezugsquelle der Updates**
  
Standardmäßig werden Updates nach Installation der Skype for Business-App aus dem Internet heruntergeladen, sobald Sie von Microsoft bereitgestellt werden. Wenn Sie mehr Kontrolle über den Zeitpunkt oder die Installationsquelle der Updates haben möchten, können Sie dies mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren
  
Viele Organisationen etwa möchten Updates vor der Bereitstellung im gesamten Unternehmen zunächst an einer Gruppe von Benutzern testen. Sie können dies tun, indem Sie die Skype for Business-App mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie so konfigurieren, dass Updates von einem bestimmten Speicherort in Ihrem Netzwerk statt automatisch über das Internet bezogen werden Anschließend können Sie die Updates mit dem Office-Bereitstellungstool monatlich in ihr lokales Netzwerk herunterladen.
  
Weitere Informationen zur Funktionsweise von Updates für Office 365-Software finden Sie in den folgenden Artikeln:
  
- [Übersicht über den Updateprozess für Microsoft 365-Apps für Unternehmen](https://technet.microsoft.com/library/dn761709.aspx)
    
- [Auswählen, wie Updates für Microsoft 365-Apps für Unternehmen verwaltet werden](https://technet.microsoft.com/library/dn761707.aspx)
    
- [Konfigurieren von Updateeinstellungen für Microsoft 365-Apps für Unternehmen](https://technet.microsoft.com/library/dn761708.aspx)
    
  **Bezug von Funktionsupdates planen**
  
Zusätzlich zur Bezugsquelle von Updates können Sie auch steuern, wie oft Sie neue Funktionen für den Skype for Business-Client erhalten. Folgende zwei Möglichkeiten stehen zur Verfügung:
  
- Funktionsupdates jeden Monat erhalten, sofern neue Funktionen zur Verfügung stehen
    
- Funktionsupdates alle sechs Monate erhalten
    
Manche Organisationen möchten Zeit haben, um neue Funktionen zu testen, und Funktionsupdates daher nur zweimal im Jahr statt monatlich erhalten.
  
Sie können steuern, wie oft Sie Funktionsupdates erhalten, indem Sie den Updatekanal mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren. Über den monatlichen Kanal erhalten Sie Funktionsupdates (ungefähr) monatlich, über den halbjährlichen Kanal dagegen alle sechs Monate. Weitere Informationen zu Kanälen finden Sie unter [Übersicht über die Update Kanäle für Microsoft 365-Apps für Unternehmen](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
