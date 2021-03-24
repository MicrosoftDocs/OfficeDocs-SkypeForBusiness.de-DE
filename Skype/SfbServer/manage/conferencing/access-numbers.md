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
description: 'Zusammenfassung: Informationen zum Verwalten von Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server.'
ms.openlocfilehash: 4008293015beaa684f9a3d9fa0ec0dedf05e5b2b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099151"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Verwalten von Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Zugriffsnummern für Einwahlkonferenzen in Skype for Business Server verwalten.
  
Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt. 
  
In diesem Thema wird das Anzeigen, Ändern oder Löschen vorhandener Zugriffsnummern für Einwahlkonferenzen beschrieben. Weitere Informationen zum Erstellen von ersten Einwahlnummern finden Sie unter [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen

Sie können Zugriffsnummern für Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell anzeigen.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Anzeigen von Einwahlzugriffsnummern mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.
    
5. Aktivieren **Sie in Bearbeiten** das Kontrollkästchen **Details** anzeigen.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Anzeigen von Einwahlzugriffsnummern mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Anzeigen von Informationen zu Einwahlnummern das **Cmdlet Get-CsDialInConferencingAccessNumber.**
  
Der folgende Befehl gibt eine Auflistung aller Zugriffsnummern für Einwahlkonferenzen zurück, die für die Verwendung in der Organisation konfiguriert sind: 
  
```PowerShell
Get-CsDialInConferencingAccessNumber
```

Im Folgenden finden Sie ein Beispiel für die Art der zurückgegebenen Informationen:
  
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

Sie können Einwahlzugriffsnummern mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell ändern.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ändern von Einwahlzugriffsnummern mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie **auf** der Seite Einwahlzugriffsnummer auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten,** und klicken Sie dann auf **Details anzeigen**.
    
    > [!NOTE]
    > Die Verwendung des Suchfelds zum Suchen nach dem Inhalt einer Spalte in der Liste der Einwahlnummern führt möglicherweise nicht zu den von Ihnen erwarteten Ergebnissen. Sortieren Sie stattdessen die Liste nach der Spalte von Interesse, um die Einwahlnummer zu identifizieren, die Sie anzeigen oder ändern möchten. 
  
5. Geben **Sie unter** Anzeigenummer die Telefonnummer ein, die Telefonbenutzer im Telefonnetz (Public Switched Telephone Network, PSTN) wählen, um an einer Konferenz teilnehmen zu können. 
    
    Diese Nummer wird in Besprechungseinladungen und auf der Webseite "Einstellungen für Einwahlkonferenzen" angezeigt.
    
6. Geben **Sie unter** Anzeigename eine Beschreibung für die Einwahlzugriffsnummer ein. Dies ist der Name, der der Einwahlzugriffsnummer in den Skype for Business-Suchergebnissen zugeordnet ist.
    
    Dieser Name wird im Client angezeigt, wenn ein Benutzer die Zugriffsnummer aufruft. 
    
7. Geben **Sie im Zeilen-URI** die E.164-Nummer der Einwahlnummer im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    > [!NOTE]
    > Der gleiche Zeilen-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. 
  
8. Gehen **Sie in SIP-URI** wie folgt vor:
    
   Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht beschränkt auf Anrufbenachrichtigungen und frühere Versionen von Lync-Clients.
    
    > [!NOTE]
    > Der gleiche SIP-URI kann nicht von einer anderen Zugriffsnummer für Einwahlkonferenzen wiederverwendet werden. Der SIP-URI kann nach dem Erstellen der Zugriffsnummer nicht mehr geändert werden. Die einzige Möglichkeit, den SIP-URI zu ändern, ist das Löschen und Neu erstellen der Zugriffsnummer. 
  
   Klicken Sie im Dropdownlistenfeld auf die Domäne der Konferenztelefonanwendung, die diese Einwahlnummer unterstützt.
    
9. Klicken **Sie in Pool** auf den Pool, in dem die Instanz der Konferenz attendant ausgeführt wird, die diese Einwahlzugriffsnummer unterstützt.
    
    > [!NOTE]
    > Wenn Sie den Pool ändern müssen, nachdem Sie die Zugriffsnummer erstellt haben, müssen Sie das **Cmdlet Move-CsApplicationEndpoint** verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken **Sie in primärer** Sprache auf die Sprache, in der Eingabeaufforderungen für diese Einwahlnummer abgespielt werden. 
    
    Die primäre Sprache ist die Sprache, die die Konferenz attendant zum Beantworten des Anrufs verwendet. Unterstützte Sprachen werden zusammen mit jeder Zugriffstelefonnummer auf der Webseite "Einstellungen für Einwahlkonferenzen" angezeigt.
    
11. (Optional) Klicken Sie in sekundären **Sprachen (maximal vier)** auf **Hinzufügen,** wählen Sie eine oder mehrere zusätzliche Sprachen aus, die Sie für Anrufer dieser Einwahlnummer unterstützen möchten, und klicken Sie dann auf **OK**. 
    
    Sie können bis zu vier sekundäre Sprachen für jede Einwahlzugriffsnummer auswählen. Benutzer können eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben, wenn sie sich bei einer Konferenz einwählen.
    
12. Klicken Sie zum Hinzufügen einer Region für die Einwahlnummer unter Zugeordnete Regionen auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahlnummer zugeordnet sind, und klicken Sie dann auf **OK**.
    
13. Klicken Sie zum Löschen einer Region aus der Einwahlnummer unter Zugeordnete Regionen auf die Region, die Sie löschen möchten, und klicken Sie dann auf **Entfernen**.
    
14. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ändern von Einwahlzugriffsnummern mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Ändern von Einwahlnummern das **Cmdlet Set-CsDialInConferencingAccessNumber.**
  
Mit dem folgenden Befehl wird die DisplayName-Eigenschaft für die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätsnamen sip:RedmondDialIn@litwareinc.com. In diesem Beispiel wird der Anzeigename auf "Redmond Dial-In Access Number" festgelegt:
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

Im nächsten Beispiel wird die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätszeichen sip:RedmondDialIn@litwareinc.com geändert, um zwei Regionen zu umfassen: Redmond und Seattle. Hierzu wird der Parameter "Region" aufgerufen, gefolgt von den beiden Regionen (zwei durch Kommas voneinander getrennte Werte). Beachten Sie, dass beim Ausführen dieses Befehls ein Fehler auftreten kann, wenn die beiden Regionen ("Redmond" und "Seattle") noch nicht in den Wähleinstellungen definiert wurden.
  
```PowerShell
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Weitere Informationen finden Sie unter [Set-CsDialInConferencingAccessNumber](/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen

Sie können eine Zugriffsnummer für Einwahlkonferenzen löschen, indem Sie die Skype for Business Server-Systemsteuerung oder die Skype for Business Server-Verwaltungsshell verwenden.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.
    
5. Klicken Sie auf **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Löschen einer Zugriffsnummer für **Einwahlkonferenzen die Remove-CsDialInConferencingAccessNumber**.
  
Mit dem folgenden Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit identitäts sip:RedmondDialInAccess@litwareinc.com:
  
```PowerShell
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region "Nordwest" zugeordnet sind:
  
```PowerShell
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Mit dem nächsten Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, wobei Italienisch die primäre Sprache ist:
  
```PowerShell
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Weitere Informationen finden Sie unter [Remove-CsDialInConferencingAccessNumber](/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
