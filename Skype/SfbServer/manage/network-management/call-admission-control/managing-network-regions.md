---
title: Verwalten von Netzwerkregionen
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Netzwerkregion* sind die Netzwerkhubs oder Backbones, die bei der Konfiguration der Anrufsteuerung, E9-1-1 und Medienumgehung verwendet werden.
ms.openlocfilehash: 5d0a40576098ceb641bdc677a551908b6a23044b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843868"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Verwalten von Netzwerkregionen in Skype for Business Server

Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Verwenden Sie die folgenden Verfahren, um Netzwerkregionen anzuzeigen, zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen, da dieselben Netzwerkregionen für weitere Enterprise VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. 

Verwenden Sie die Verfahren in diesem Artikel, um Netzwerkregioneninformationen anzuzeigen oder Netzwerkregionen zu erstellen, zu ändern oder zu löschen. 

## <a name="view-network-region-information"></a>Anzeigen von Netzwerkregioneninformationen 


Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können Skype for Business Server Systemsteuerung verwenden, um Netzwerkregionen anzuzeigen. Netzwerkregionen beinhalten Einstellungen, die festlegen, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In diesem Thema wird erklärt, wie vorhandene Netzwerkregionen angezeigt werden. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einer Netzwerkregion mit Skype for Business Server Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie anzeigen möchten.
  
    > [!NOTE]  
    > Sie können immer nur eine Region anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerkregioneninformationen mithilfe Windows PowerShell Cmdlets

Sie können Netzwerkregioneninformationen mithilfe von Windows PowerShell und dem Cmdlet **"Get-CsNetworkRegion"** anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. 

### <a name="to-view-network-region-information"></a>So zeigen Sie Netzwerkregioneninformationen an

  - Um Informationen zu allen Netzwerkregionen anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
    **Get-CsNetworkRegion**
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
    Identität: Pacific Pacific Pacific<br/>
    Beschreibung:<br/>
    BypassID : 3b232b84-2c1d-4da2-8181-e9330bafebe9<br/>
    CentralSite : Site:Redmond1<br/>
    BWAlternatePaths : {BWPolicyModality=Audio; AlternatePath=True, <br/>
                       BWPolicyModality=Video; AlternatePath=True}<br/>
    NetworkRegionID : Pacific Northwest<br/>

Weitere Informationen finden Sie im Hilfethema für das [Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)-Cmdlet.


## <a name="create-or-modify-network-regions"></a>Erstellen oder Ändern von Netzwerkregionen 

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können die Skype for Business Server Systemsteuerung verwenden, um Netzwerkregionen zu konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen. 

### <a name="to-create-a-network-region"></a>So erstellen Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf **Neu**.

5.  Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein. Dieser Wert muss innerhalb Ihrer Skype for Business Server Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.

7.  Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet. Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern. Ausführliche Informationen finden Sie unter [Verwalten der Anrufsteuerung für Websites.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>So ändern Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

6.  Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.


## <a name="delete-existing-network-regions"></a>Löschen vorhandener Netzwerkregionen 

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können die Skype for Business Server Systemsteuerung verwenden, um Netzwerkregionen zu konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene Netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region"></a>So löschen Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **"Region"** auf die Region, die Sie löschen möchten.
  
    > [!NOTE]  
    > Sie können mehrere Regionen gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Bereiche aus, während Sie die STRG-TASTE gedrückt halten. Oder klicken Sie im Menü **"Bearbeiten"** auf **"Alle auswählen",** um alle Regionen auszuwählen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


    > [!WARNING]  
    > Eine Netzwerkregion kann nicht entfernt werden, wenn sie einem Netzwerkstandort zugeordnet ist. Wenn Sie versuchen, eine Region zu entfernen, die einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt. Um festzustellen, ob eine Region mit Websites verknüpft ist, wählen Sie die Region aus, und klicken Sie dann im Menü **"Bearbeiten"** auf **"Details anzeigen".**


## <a name="see-also"></a>Siehe auch

[Verwalten von Netzwerkregionenrouten](managing-network-region-routes.md)

[New-CsNetworkRegion](/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](/powershell/module/skype/Get-CsNetworkRegionLink)