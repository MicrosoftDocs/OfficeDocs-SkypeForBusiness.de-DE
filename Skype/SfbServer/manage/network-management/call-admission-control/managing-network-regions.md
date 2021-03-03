---
title: Verwalten von Netzwerkregionen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Netzwerkregion* sind die Netzwerkhubs oder Backbones, die bei der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet werden.
ms.openlocfilehash: 14c8004ddd14c0a37c25d700edae845ac9adfe29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816415"
---
# <a name="managing-network-regions-in-skype-for-business-server"></a>Verwalten von Netzwerkregionen in Skype for Business Server

Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird. Verwenden Sie die folgenden Verfahren, um Netzwerkregionen anzuzeigen, zu erstellen oder zu ändern. Wenn Sie beispielsweise bereits Netzwerkregionen für eine VoIP-Funktion erstellt haben, müssen Sie keine neuen Netzwerkregionen erstellen, da dieselben Netzwerkregionen für weitere Enterprise VoIP-Funktionen verwendet werden können. Sie müssen jedoch möglicherweise eine vorhandene Definition einer Netzwerkregion ändern, um funktionsspezifische Einstellungen anzuwenden. Wenn Sie z. B. Netzwerkregionen für E9-1-1 erstellt haben (denen kein zentraler Standort zugeordnet werden muss) und Sie zu einem späteren Zeitpunkt die Anrufsteuerung bereitstellen, müssen Sie die Definitionen der Netzwerkregionen ändern und einen zentralen Standort angeben. 

Verwenden Sie die Verfahren in diesem Artikel, um Informationen zu Netzwerkregionen anzeigen oder Netzwerkregionen zu erstellen, zu ändern oder zu löschen. 

## <a name="view-network-region-information"></a>Anzeigen von Informationen zur Netzwerkregion 


Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung zum Anzeigen von Netzwerkregionen verwenden. Netzwerkregionen beinhalten Einstellungen, die festlegen, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In diesem Thema wird erklärt, wie vorhandene Netzwerkregionen angezeigt werden. 

### <a name="to-view-information-about-a-network-region-with-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zu einer Netzwerkregion mit der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie anzeigen möchten.
  
    > [!NOTE]  
    > Sie können immer nur eine Region anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerkregionsinformationen mithilfe Windows PowerShell Cmdlets

Sie können Informationen zur Netzwerkregion mithilfe Windows PowerShell **Cmdlets "Get-CsNetworkRegion"** anzeigen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 

### <a name="to-view-network-region-information"></a>So zeigen Sie Informationen zur Netzwerkregion an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkregionen den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkRegion
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

Weitere Informationen finden Sie im Hilfethema für das [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)-Cmdlet.


## <a name="create-or-modify-network-regions"></a>Erstellen oder Ändern von Netzwerkregionen 

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Netzwerkregionen zu konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server-Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema zum Erstellen und Ändern von Netzwerkregionen. 

### <a name="to-create-a-network-region"></a>So erstellen Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf **Neu**.

5.  Geben Sie auf der Seite **Neue Region** im Feld **Name** einen Wert ein. Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Zentraler Standort** den zentralen Standort für diese Netzwerkregion aus.

7.  Das Kontrollkästchen **Alternativen Audiopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Audioanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

8.  Das Kontrollkästchen **Alternativen Videopfad aktivieren** ist standardmäßig aktiviert. Diese Einstellung legt fest, ob Videoanrufe über einen alternativen Pfad weitergeleitet werden, wenn der primäre Pfad keine angemessene Bandbreite bietet. Deaktivieren Sie dieses Kontrollkästchen nur dann, wenn alternative Pfade im Internet deaktiviert werden müssen. Wenn Internetanrufe vorgesehen sind, muss dieses Kontrollkästchen unabhängig von den Bandbreiteneinstellungen aktiviert sein.

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu dieser Region ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit ausführen**.

Die Tabelle **Zugeordnete Standorte** wird zum Erstellen einer Netzwerkregion nicht verwendet. Sie ordnen einer Region einen Standort zu, wenn Sie den Standort erstellen oder ändern. Weitere Informationen finden Sie unter [Verwalten der Anrufsteuerung für Standorte.](managing-call-admission-control-for-sites.md)

### <a name="to-modify-a-network-region"></a>So ändern Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie auf der Seite **Region** auf die Region, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details einblenden**.

6.  Auf der Seite **Region bearbeiten** können Sie die Einstellungen zum Aktivieren und Deaktivieren von alternativen Pfaden für Audio und Video ändern, und Sie können die Beschreibung bearbeiten (ausführliche Informationen finden Sie unter "So erstellen Sie eine Netzwerkregion" weiter oben in diesem Thema).

7.  Klicken Sie auf **Commit ausführen**.

Sie können die Option **Zugeordnete Standorte** auf dieser Seite nicht ändern. Die Liste der zugeordneten Standorte wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Standorte sich die Änderung der Regioneneinstellungen auswirkt.


## <a name="delete-existing-network-regions"></a>Löschen vorhandener Netzwerkregionen 

Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt. Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein. Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Netzwerkregionen zu konfigurieren. Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind. In der Skype for Business Server-Systemsteuerung können Sie eine Netzwerkregion erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene Netzwerkregionen zu löschen. 

### <a name="to-delete-a-network-region"></a>So löschen Sie eine Netzwerkregion

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Region".**

4.  Klicken Sie **auf der** Seite "Region" auf die Region, die Sie löschen möchten.
  
    > [!NOTE]  
    > Sie können mehrere Regionen gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Bereiche aus, während Sie die STRG-TASTE gedrückt halten. Wenn Sie alle Regionen auswählen möchten, klicken **Sie** im Menü "Bearbeiten" **auf** "Alle auswählen".

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.


    > [!WARNING]  
    > Eine Netzwerkregion kann nicht entfernt werden, wenn sie einem Netzwerkstandort zugeordnet ist. Wenn Sie versuchen, eine Region zu entfernen, die einem Standort zugeordnet ist, wird eine Fehlermeldung angezeigt. Um zu sehen, ob eine Region Standorten zugeordnet ist, wählen Sie die Region aus, und klicken Sie dann im Menü "Bearbeiten" auf **"Details** anzeigen". 


## <a name="see-also"></a>Siehe auch

[Verwalten von Netzwerkregionsrouten](managing-network-region-routes.md)

[New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  

[Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  

[Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  

[Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
