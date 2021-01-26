---
title: 'Verwalten von Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server '
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
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Zusammenfassung: Erfahren Sie, wie Sie Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: 868d757edc6728254c1ab09d22398cd3dc60901b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806485"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Verwalten von Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server verwalten.
  
Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt. 
  
In diesem Thema wird beschrieben, wie Sie vorhandene Zugriffsnummern für Einwahlkonferenzen anzeigen, ändern oder löschen. Weitere Informationen zum Erstellen von ersten Zugriffsnummern für die Einwahl finden Sie unter "Konfigurieren von Einwahlkonferenzen [in Skype for Business Server".](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen

Sie können Zugriffsnummern für Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell anzeigen.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Zugriffsnummern für die Einwahl mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.
    
5. Aktivieren **Sie in "Bearbeiten"** das **Kontrollkästchen Details** anzeigen.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Zugriffsnummern für die Einwahl mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Anzeigen von Informationen zu Zugriffsnummern für die Einwahl das **Cmdlet "Get-CsDialInConferencingAccessNumber".**
  
Der folgende Befehl gibt eine Auflistung aller Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in der Organisation konfiguriert sind: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Nachfolgend finden Sie ein Beispiel für den Typ der zurückgegebenen Informationen:
  
<pre>
Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                     CN=Application Contacts,CN=RTCService=Services,
                     CN=Configuration,DC=litwareinc,DC=com
PrimaryUri         : sip:testnumber@litwareinc.com
DisplayName        : Test
DisplayNumber      : 1-425-555-1019
LineUri            : tel:+14255551019
PrimaryLanguage    : en-US
SecondaryLanguages : {}
Pool               : atl-cs-001.litwareinc.com
HostingProvider    :
Regions            : {US}
</pre>

Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Ändern von Zugriffsnummern für Einwahlkonferenzen

Sie können Zugriffsnummern für die Einwahl mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell ändern.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ändern von Zugriffsnummern für die Einwahl mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie **auf** der Seite "Zugriffsnummer für Einwahl" auf eine der Zugriffsnummern für die Einwahl in der Liste, klicken Sie auf "Bearbeiten" **und** dann auf **"Details anzeigen".**
    
    > [!NOTE]
    > Die Verwendung des Suchfelds zum Suchen nach dem Inhalt einer Spalte in der Liste der Zugriffsnummern für die Einwahl liefert möglicherweise nicht die von Ihnen erwarteten Ergebnisse. Sortieren Sie stattdessen die Liste nach der spalte, die für Sie von Interesse ist, um die Zugriffsnummer für die Einwahl zu identifizieren, die Sie anzeigen oder ändern möchten. 
  
5. Geben **Sie unter "Anzeigenummer"** die Telefonnummer ein, die Benutzer von Festnetztelefonen (Public Switched Telephone Network, PSTN) wählen, um an einer Konferenz teil zu nehmen. 
    
    Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.
    
6. Geben **Sie im Anzeigenamen** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der der Zugriffsnummer für die Einwahl in den Skype for Business-Suchergebnissen zugeordnet ist.
    
    Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer aufruft. 
    
7. Geben **Sie im Zeilen-URI** die E.164-Nummer der Einwahlnummer im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    > [!NOTE]
    > Der gleiche Leitungs-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. 
  
8. Gehen **Sie im SIP-URI** wie folgt vor:
    
   Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht beschränkt auf Anrufbenachrichtigungen und frühere Versionen von Lync-Clients.
    
    > [!NOTE]
    > Derselbe SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. Der SIP-URI kann nach dem Erstellen der Zugriffsnummer nicht mehr geändert werden. Die einzige Möglichkeit, den SIP-URI zu ändern, ist das Löschen und Neuerstellung der Zugriffsnummer. 
  
   Klicken Sie im Dropdownlistenfeld auf die Domäne der Konferenztelefonanrufanwendung, die diese Zugriffsnummer für die Einwahl unterstützt.
    
9. Klicken Sie im **Pool** auf den Pool, in dem die Instanz der Konferenztelefon attendant ausgeführt wird, die diese Zugriffsnummer für die Einwahl unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Pool nach dem Erstellen der Zugriffsnummer ändern müssen, müssen Sie das **Cmdlet "Move-CsApplicationEndpoint"** verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken **Sie in der primären** Sprache auf die Sprache, in der Ansforderungen für diese Zugriffsnummer für die Einwahl abgespielt werden. 
    
    Die primäre Sprache ist die Sprache, die die Konferenz attendant zum Beantworten des Anrufs verwendet. Unterstützte Sprachen werden zusammen mit jeder Zugriffstelefonnummer auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.
    
11. (Optional) Klicken Sie in sekundären Sprachen **(maximal vier)** auf "Hinzufügen", wählen Sie eine oder mehrere zusätzliche Sprachen aus, die Sie für Anrufer dieser Zugriffsnummer für die Einwahl unterstützen möchten, und klicken Sie dann auf **"OK".** 
    
    Sie können bis zu vier sekundäre Sprachen für jede Zugriffsnummer für die Einwahl auswählen. Benutzer können vor der Eingabe der Konferenz-ID eine sekundäre Sprache auswählen, wenn sie sich in eine Konferenz einwählen.
    
12. Klicken Sie zum Hinzufügen einer Region für die Zugriffsnummer für die Einwahl unter "Zugeordnete Regionen" auf "Hinzufügen", klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Zugriffsnummer für die Einwahl zugeordnet sind, und klicken Sie dann auf **OK**.
    
13. Klicken Sie zum Löschen einer Region aus der Zugriffsnummer für die Einwahl unter "Zugeordnete Regionen" auf die Region, die Sie löschen möchten, und klicken Sie dann auf **"Entfernen".**
    
14. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ändern von Zugriffsnummern für die Einwahl mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **"Set-CsDialInConferencingAccessNumber",** um Zugriffsnummern für die Einwahl zu ändern.
  
Mit dem folgenden Befehl wird die Eigenschaft "DisplayName" für die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätsnamen sip:RedmondDialIn@litwareinc.com. In diesem Beispiel wird der Anzeigename auf "Redmond Dial-In Access Number" festgelegt:
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Im nächsten Beispiel wird die Zugriffsnummer für Einwahlkonferenzen mit dem Identitäts sip:RedmondDialIn@litwareinc.com geändert, um zwei Regionen zu umfassen: Redmond und Seattle. Hierzu wird der Parameter "Region" aufgerufen, gefolgt von den beiden Regionen (zwei durch Kommas voneinander getrennte Werte). Beachten Sie, dass beim Ausführen dieses Befehls ein Fehler auftreten kann, wenn die beiden Regionen ("Redmond" und "Seattle") noch nicht in den Wähleinstellungen definiert wurden.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Weitere Informationen finden Sie unter [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen

Sie können eine Zugriffsnummer für Einwahlkonferenzen löschen, indem Sie die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.
    
5. Klicken Sie auf **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Löschen einer Zugriffsnummer für Einwahlkonferenzen die **Remove-CsDialInConferencingAccessNumber**.
  
Der folgende Befehl löscht die Zugriffsnummer für Einwahlkonferenzen mit sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region "Northwest" zugeordnet sind:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, wobei Italienisch die primäre Sprache ist:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Weitere Informationen finden Sie unter [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

