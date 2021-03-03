---
title: Verwalten der Anrufsteuerung für Standorte
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
description: Bei Netzwerkstandorten handelt es sich um Büros oder Zweigstellen innerhalb der einzelnen Netzwerkregionen von Bereitstellungen mit Anrufsteuerung, E9-1-1 und Medienumgehung.
ms.openlocfilehash: dbe02c78c40cab48a79d7c63d3c6239b4ae59458
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816455"
---
# <a name="managing-call-admission-control-for-sites-in-skype-for-business-server"></a>Verwalten der Anrufsteuerung für Standorte in Skype for Business Server

Bei Netzwerkstandorten handelt es sich um Büros oder Zweigstellen innerhalb der einzelnen Netzwerkregionen von Bereitstellungen mit Anrufsteuerung, E9-1-1 und Medienumgehung. Verwenden Sie die Verfahren in diesem Artikel, um die Anrufsteuerung für Netzwerkstandorte zu konfigurieren.

## <a name="configure-network-site-links"></a>Konfigurieren von Netzwerkstandortverbindungen

Innerhalb einer Anrufsteuerungskonfiguration können Sie standortübergreifende Netzwerkrichtlinien erstellen, die Bandbreiteneinschränkungen zwischen Standorten definieren, die direkt verknüpft sind. Wenn Netzwerkstandorte eine direkte Verbindung teilen, können Bandbreiteneinschränkungen für Audio- und Videoverbindungen zwischen diesen zwei Standorten definiert werden. Die Skype for Business Server-Systemsteuerung kann nicht zum Konfigurieren von Netzwerkstandortrichtlinien verwendet werden. Dies kann nur mithilfe von Cmdlets aus der Skype for Business Server-Verwaltungsshell geschehen. Sie können eine Netzwerkstandortverbindung (auch als standortübergreifende Netzwerkrichtlinie bezeichnet) in der Skype for Business Server-Verwaltungsshell erstellen, ändern und entfernen.

### <a name="to-create-a-network-site-link"></a>So erstellen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server Management Shell".**

3.  Geben Sie an der Eingabeaufforderung den folgenden Befehl ein, und verwenden Sie dabei die für Ihre Konfiguration gültigen Werte:
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    In diesem Beispiel wird eine neue Netzwerkstandortverbindung namens "Reno Portland" erstellt, mit der Bandbreiteneinschränkungen zwischen den \_ Netzwerkstandorten "Reno" und "Portland" gesetzt werden. Die Netzwerkstandorte und das Bandbreitenrichtlinienprofil müssen bereits vorhanden sein, bevor Sie diesen Befehl ausführen.

Ausführliche Parameterbeschreibungen finden Sie unter [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy). Zum Abrufen einer Liste der Bandbreitenrichtlinienprofile, die auf die Netzwerkstandortverknüpfung angewendet werden können, verwenden Sie das Cmdlet **Get-CsNetworkBandwidthPolicyProfile**. Weitere Informationen finden Sie unter [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

### <a name="to-modify-a-network-site-link"></a>So ändern Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server-Verwaltungsshell".**

3.  Verwenden Sie das Cmdlet **Set-CsNetworkInterSitePolicy**, um die Eigenschaften einer Netzwerkstandortverknüpfung zu ändern. Sie können entweder einen oder beide verbundenen Standorte ändern, und Sie können das der Verknüpfung zugeordnete Bandbreitenrichtlinienprofil bearbeiten. Hier ist ein Beispiel für das Ändern des Bandbreitenrichtlinienprofils einer Standortverknüpfung namens "Reno \_ Portland":
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

Ausführliche Parameterbeschreibungen finden Sie unter [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy).


### <a name="to-delete-a-network-site-link"></a>So löschen Sie eine Netzwerkstandortverknüpfung

1.  Melden Sie sich bei dem Computer, auf dem Skype for Business Server Management Shell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an.

2.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie **auf "Start",**"Alle **Programme",** **"Skype for Business Server"** und dann auf **"Skype for Business Server Management Shell".**

3.  Verwenden Sie das Cmdlet **Remove-CsNetworkInterSitePolicy**, um eine Netzwerkstandortverknüpfung zu löschen. Im folgenden Beispiel wird die Netzwerkstandortverknüpfung "Reno \_ Portland" gelöscht:
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

Ausführliche Parameterbeschreibungen finden Sie unter [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy).


## <a name="view-network-site-information"></a>Anzeigen von Netzwerkstandortinformationen

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können Informationen zum Netzwerkstandort entweder in der Skype for Business Server-Systemsteuerung oder in der Skype for Business Server-Verwaltungsshell anzeigen. 

### <a name="to-view-network-site-information-in-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zum Netzwerkstandort in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standort".**

4.  Klicken Sie auf der Seite **Website** auf die Website, die Sie anzeigen möchten.
 
    > [!NOTE]  
    > Sie können jeweils nur Informationen für einen Standort anzeigen.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerkstandortinformationen mithilfe Windows PowerShell Cmdlets

Sie können Netzwerkstandortinformationen mithilfe von Windows PowerShell und dem cmdlet Get-CsNetworkSite anzeigen. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell. 

### <a name="to-view-network-site-information"></a>So zeigen Sie Netzwerkstandortinformationen an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkstandorten den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkSite
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite).


## <a name="create-or-modify-network-sites"></a>Erstellen oder Ändern von Netzwerkstandorten 

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und sie Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. Über die Skype for Business Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen Netzwerkstandort zu erstellen oder zu ändern. 

### <a name="to-create-a-network-site"></a>So erstellen Sie einen Netzwerkstandort

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standort".**

4.  Klicken Sie auf der Seite **Standort** auf **Neu**.

5.  Geben Sie unter **Neuer Standort** im Feld **Name** einen Namen für den Standort ein.

    > [!NOTE]  
    > Websitenamen müssen innerhalb der Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **Region** eine Netzwerkregion aus, die diesem Standort zugeordnet werden soll.

7.  (Optional) Wenn Sie Bandbreitenbeschränkungen für Audio- oder Videoanrufe für diesen Standort festlegen möchten, wählen Sie das Bandbreitenrichtlinienprofil mit den passenden Einstellungen in der Dropdownliste **Bandbreitenrichtlinie** aus.
 
    > [!NOTE]  
    > Sie können die Details der verfügbaren Bandbreitenrichtlinienprofile auf der Seite **"Richtlinienprofil"** der **Netzwerkkonfigurationsgruppe** anzeigen oder ein neues Bandbreitenrichtlinienprofil erstellen. Weitere Informationen finden Sie unter [Verwalten von Netzwerkbandbreitenrichtlinienprofilen.](managing-network-bandwidth-policy-profiles.md)

8.  (Optional) Wenn Sie Ortungseinstellungen für diesen Standort bereitstellen möchten, wählen Sie in der Dropdownliste **Ortungsrichtlinie** eine Ortungsrichtlinie aus.

    > [!NOTE]  
    > Die Ortungsrichtlinie weist dem Standort bestimmte E9-1-1- und Clientstandorteinstellungen zu. Auf der Seite **Ortungsrichtlinie** in der Gruppe **Netzwerkkonfiguration** können Sie die Details der verfügbaren Ortungsrichtlinien anzeigen oder eine neue Ortungsrichtlinie erstellen. 

9.  (Optional) Geben Sie im Feld **Beschreibung** einen Wert zum Bereitstellen weiterer Informationen zu diesem Standort ein, die nicht durch den Namen allein vermittelt werden können.

10. Klicken Sie auf **Commit**.

    > [!NOTE]  
    > Beim Erstellen eines neuen Netzwerkstandorts verwenden Sie nicht die Tabelle **Zugeordnete Subnetze**. Sie ordnen einem Standort ein Subnetz zu, wenn Sie das Subnetz erstellen oder ändern. Weitere Informationen finden Sie unter ["Verwalten von Netzwerksubnetzen".](managing-network-subnets.md)

### <a name="to-modify-a-network-site"></a>So ändern Sie einen Netzwerkstandort

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standort".**

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Auf der Seite **Standort bearbeiten** können Sie die Beschreibung, die Region, das Bandbreitenrichtlinienprofil und die Ortungsrichtlinie für den Standort ändern. Weitere Informationen finden Sie unter [So erstellen Sie oben einen Netzwerkstandort.](#to-create-a-network-site)

7.  Klicken Sie auf **Commit**.

Sie können die Tabelle **Zugeordnete Subnetze** auf dieser Seite nicht ändern. Die Liste der zugeordneten Subnetze wird zu Referenzzwecken angezeigt, damit Sie wissen, auf welche Subnetze sich die Änderung der Standorteinstellungen auswirkt.


## <a name="delete-an-existing-network-site"></a>Löschen eines vorhandenen Netzwerkstandorts

Netzwerkstandorte sind Büros, Niederlassungen oder Standorte, die in jeder Region einer Bereitstellung für einen Anrufsteuerungsdienst oder Notfalldienst (E9-1-1) konfiguriert sind. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Websites zu konfigurieren und sie Regionen zuzuordnen. Eine Netzwerkregion für Nordamerika ist beispielsweise Netzwerkstandorten wie Chicago, Redmond und Vancouver zugeordnet. Ein Anrufsteuerungsdienst-Netzwerkstandort muss für jeden Standort einer Organisation erstellt werden, selbst wenn der jeweilige Standort keine Bandbreiteneinschränkungen aufweist. Über die Skype for Business Server-Systemsteuerung können Sie Netzwerkstandorte erstellen, ändern und löschen. Verwenden Sie das folgende Verfahren, um einen vorhandenen Netzwerkstandort zu löschen. Weitere Informationen zum Erstellen oder Ändern von Netzwerkstandorten finden Sie unter [Verwalten der Anrufsteuerung für Standorte.](managing-call-admission-control-for-sites.md)


### <a name="to-delete-a-network-site"></a>So löschen Sie einen Netzwerkstandort

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Standort".**

4.  Klicken Sie auf der Seite **Standort** auf den Standort, den Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehrere Standorte in einem Arbeitsschritt löschen. Drücken Sie hierzu STRG, und wählen Sie bei gedrückter STRG-TASTE mehrere Standorte aus. Wenn Sie alle Standorte auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.
    

    > [!WARNING]  
    > Ein Netzwerkstandort kann nicht gelöscht werden, wenn er einem Netzwerksubnetz zugeordnet ist. Wenn Sie versuchen, einen einem Subnetz zugeordneten Standort zu entfernen, wird eine Fehlermeldung ausgegeben. Um zu überprüfen, ob ein Standort einem Subnetz zugeordnet ist, klicken Sie auf den Standort und anschließend im Menü **Bearbeiten** auf **Details anzeigen**.


## <a name="see-also"></a>Siehe auch


[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) 
 
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  

[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  

[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  

[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[New-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)

[Set-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)

[Remove-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  

[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
