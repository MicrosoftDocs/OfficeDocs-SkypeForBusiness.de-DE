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
ms.localizationpriority: medium
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Zusammenfassung: Erfahren Sie, wie Sie Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: d76d6135f32b3ea46368080169bf288a637e7546
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011519"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Verwalten von Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server verwalten.
  
Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt. 
  
In diesem Thema wird beschrieben, wie Sie vorhandene Zugriffsnummern für Einwahlkonferenzen anzeigen, ändern oder löschen. Weitere Informationen zum Erstellen anfänglicher Einwahlnummern finden Sie unter [Konfigurieren von Einwahlkonferenzen in Skype for Business Server.](../../deploy/deploy-conferencing/dial-in-conferencing.md)
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen

Sie können Zugriffsnummern für Einwahlkonferenzen über Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell anzeigen.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Einwahlnummern mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.
    
5. Aktivieren Sie in **"Bearbeiten"** das Kontrollkästchen **"Details anzeigen".**
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Einwahlnummern mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie das Cmdlet **"Get-CsDialInConferencingAccessNumber",** um Informationen zu Einwahlnummern anzuzeigen.
  
Der folgende Befehl gibt eine Auflistung aller Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in der Organisation konfiguriert sind: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Nachfolgend sehen Sie ein Beispiel für den Typ der zurückgegebenen Informationen:
  
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

Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Ändern von Zugriffsnummern für Einwahlkonferenzen

Sie können Zugriffsnummern für die Einwahl über Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell ändern.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ändern von Einwahlnummern mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **"Einwahlzugriffsnummer"** auf eine der Zugriffsnummern für die Einwahl in der Liste, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".**
    
    > [!NOTE]
    > Die Verwendung des Suchfelds zum Suchen nach dem Inhalt einer Spalte in der Liste der Einwahlnummern liefert möglicherweise nicht die erwarteten Ergebnisse. Sortieren Sie stattdessen die Liste nach der gewünschten Spalte, um die Einwahlnummer zu identifizieren, die Sie anzeigen oder ändern möchten. 
  
5. Geben Sie in der **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer wählen, um an einer Konferenz teilzunehmen. 
    
    Diese Nummer wird in Besprechungseinladungen und auf der Webseite für Einwahlkonferenzen Einstellungen angezeigt.
    
6. Geben Sie unter **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der der Einwahlzugriffsnummer in Skype for Business Suchergebnissen zugeordnet ist.
    
    Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer aufruft. 
    
7. Geben Sie im **Anschluss-URI** die E.164-Nummer der Einwahlnummer im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: `tel:+14255550200`.
    
    > [!NOTE]
    > Der gleiche Anschluss-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. 
  
8. Führen **Sie im SIP-URI** die folgenden Schritte aus:
    
   Geben Sie im Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht beschränkt auf, Anrufbenachrichtigungen und frühere Versionen von Lync-Clients.
    
    > [!NOTE]
    > Derselbe SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. Der SIP-URI kann nicht geändert werden, nachdem die Zugriffsnummer erstellt wurde. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen. 
  
   Klicken Sie im Dropdownlistenfeld auf die Domäne des Konferenzzentralenanwendung, das diese Einwahlnummer unterstützt.
    
9. Klicken Sie im **Pool** auf den Pool, in dem die Instanz von Konferenzzentrale ausgeführt wird, die diese Einwahlnummer unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Pool ändern müssen, nachdem Sie die Zugriffsnummer erstellt haben, müssen Sie das Cmdlet **"Move-CsApplicationEndpoint"** verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken Sie in der **Primären Sprache** auf die Sprache, in der Eingabeaufforderungen für diese Einwahlnummer wiedergegeben werden. 
    
    Die primäre Sprache ist die Sprache, die der Konferenzzentrale zum Annehmen des Anrufs verwendet. Unterstützte Sprachen werden zusammen mit jeder Zugriffstelefonnummer auf der Webseite für Einwahlkonferenzen Einstellungen angezeigt.
    
11. (Optional) Klicken Sie in **sekundären Sprachen (maximal vier)** auf **"Hinzufügen",** wählen Sie eine oder mehrere zusätzliche Sprachen aus, die Sie für Anrufer für diese Einwahlnummer unterstützen möchten, und klicken Sie dann auf **"OK".** 
    
    Sie können für jede Einwahlnummer bis zu vier sekundäre Sprachen auswählen. Benutzer können eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben, wenn sie sich in eine Konferenz einwählen.
    
12. Klicken Sie zum Hinzufügen einer Region für die Zugriffsnummer für die Einwahl unter **"Zugeordnete Regionen"** auf **"Hinzufügen",** klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahlnummer zugeordnet sind, und klicken Sie dann auf **"OK".**
    
13. Um eine Region aus der Einwahlnummer zu löschen, klicken Sie unter **"Zugeordnete Regionen"** auf die Region, die Sie löschen möchten, und klicken Sie dann auf **"Entfernen".**
    
14. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ändern von Einwahlnummern mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Ändern von Einwahlnummern das Cmdlet **"Set-CsDialInConferencingAccessNumber".**
  
Der folgende Befehl ändert die DisplayName-Eigenschaft für die Zugriffsnummer für Einwahlkonferenzen mit der Identität sip:RedmondDialIn@litwareinc.com. In diesem Beispiel wird der Anzeigename auf "Redmond Dial-In Access Number" festgelegt:
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Im nächsten Beispiel wird die Zugriffsnummer für Einwahlkonferenzen mit der Identität sip:RedmondDialIn@litwareinc.com geändert, um zwei Regionen einzuschließen: Redmond und Seattle. Hierzu wird der Parameter "Region" aufgerufen, gefolgt von den beiden Regionen (zwei durch Kommas voneinander getrennte Werte). Beachten Sie, dass beim Ausführen dieses Befehls ein Fehler auftreten kann, wenn die beiden Regionen ("Redmond" und "Seattle") noch nicht in den Wähleinstellungen definiert wurden.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Weitere Informationen finden Sie unter [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen

Sie können eine Zugriffsnummer für Einwahlkonferenzen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell löschen.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.
    
5. Klicken Sie auf **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Löschen einer Zugriffsnummer für Einwahlkonferenzen die **Remove-CsDialInConferencingAccessNumber**.
  
Mit dem folgenden Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit identity sip:RedmondDialInAccess@litwareinc.com gelöscht:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region "Nordost" zugeordnet sind:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, wobei Italienisch die primäre Sprache ist:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Weitere Informationen finden Sie unter [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
