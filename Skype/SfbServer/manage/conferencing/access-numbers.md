---
title: 'Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server '
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a0d64779-93de-4d82-ae35-e4454ef8b8f6
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server.'
ms.openlocfilehash: aa386b1c2dd868634539be32062ed7728e27c1e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919409"
---
# <a name="manage-dial-in-conferencing-access-numbers-in-skype-for-business-server"></a>Verwalten von Zugriffsnummern für einwahlkonferenzen in Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Zugriffsnummern für einwahlkonferenzen in Skype für Business Server verwalten.
  
Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen. Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt. 
  
In diesem Themenbereich wird beschrieben, wie bestehende Zugriffsnummern für Einwahlkonferenzen angezeigt, geändert oder gelöscht werden. Weitere Informationen zum Erstellen der anfänglichen Einwahl Zugriffsnummern finden Sie unter [Configure einwahlkonferenzen in Skype für Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
  
## <a name="view-dial-in-conferencing-access-numbers"></a>Anzeigen von Zugriffsnummern für Einwahlkonferenzen

Sie können die Zugriffsnummern für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell anzeigen.
  
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ansicht Einwahl Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **Zugriffsnummer für Einwahlkonferenz** auf die Zugriffsnummer, die Sie anzeigen möchten.
    
5. Aktivieren Sie unter **Bearbeiten** das Kontrollkästchen **Details anzeigen**.
    
### <a name="view-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ansicht Einwahl Zugriffsnummern mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Get-CsDialInConferencingAccessNumber**, um Informationen über Zugriffsnummern für die Einwahl anzuzeigen.
  
Der folgende Befehl gibt eine Auflistung von allen einwahlkonferenzen Zugriffsnummern für die Verwendung in der Organisation konfiguriert: 
  
```
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

Weitere Informationen finden Sie unter [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="modify-dial-in-conferencing-access-numbers"></a>Zugriffsnummern für Einwahlkonferenzen ändern

Sie können die Zugriffsnummer für Einwahl-Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.
  
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-control-panel"></a>Ändern der Einwahl Zugriffsnummern mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite **Zugriffsnummer für die Einwahl** auf eine der Einwahlnummern in der Liste, anschließend auf **Bearbeiten** und dann auf **Details anzeigen**.
    
    > [!NOTE]
    > Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten. 
  
5. Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen. 
    
    Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.
    
6. Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein. Dies ist der Name, der die Anzahl DFÜ-Zugriff in Skype für Suchergebnisse Business zugeordnet ist.
    
    Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt. 
    
7. Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.
    
    > [!NOTE]
    > Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden. 
  
8. Führen Sie unter **SIP-URI** die folgenden Aktionen aus:
    
   Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein. SIP-URI ist in verschiedenen Standorten, einschließlich angezeigt, aber nicht beschränkt, um Benachrichtigungen und früheren Versionen von Lync-Clients aufrufen.
    
    > [!NOTE]
    > Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen. 
  
   Klicken Sie im Dropdown-Listenfeld auf die Domäne der Konferenzzentrale Anwendung, die diese Zugriffsnummer für Einwahl unterstützt.
    
9. Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.
    
    > [!NOTE]
    > Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** verwenden oder die Zugriffsnummer löschen und neu erstellen.
  
10. Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden. 
    
    Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.
    
11. (Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**. 
    
    Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.
    
12. Klicken Sie auf **Hinzufügen**, klicken Sie auf einen oder mehrere Bereiche, die für diese Nummer Einwahlnummern Wählpläne zugeordnet sind, und klicken Sie dann auf **OK**, um eine Region für die Anzahl DFÜ-Zugriff unter **zugeordnete Regionen**, hinzuzufügen.
    
13. Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.
    
14. Klicken Sie auf **Commit ausführen**.
    
### <a name="modify-dial-in-access-numbers-by-using-skype-for-business-server-management-shell"></a>Ändern der Einwahl Zugriffsnummern mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das Cmdlet **Set-CsDialInConferencingAccessNumber**, um die Zugriffsnummern für die Einwahl zu ändern.
  
Der folgende Befehl ändert die Eigenschaft „DisplayName“ für die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätswert „sip:RedmondDialIn@litwareinc.com“. In diesem Beispiel wurde als Anzeigename „Redmond Dial-In Access Number“ festgelegt:
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -DisplayName "Redmond Dial-In Access Number"
```

In nächsten Beispiel wird die Zugriffsnummer für Einwahlkonferenzen mit dem Identitätswert „sip:RedmondDialIn@litwareinc.com“ geändert, um zwei Regionen anzugeben: „Redmond“ und „Seattle“. Hierzu wird der Parameter „Region“ aufgerufen, gefolgt von den beiden Regionen (zwei durch Kommas voneinander getrennte Werte). Beachten Sie, dass beim Ausführen dieses Befehls ein Fehler auftreten kann, wenn die beiden Regionen („Redmond“ und „Seattle“) noch nicht in den Wähleinstellungen definiert wurden.
  
```
Set-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialIn@litwareinc.com" -Regions "Redmond", "Seattle"
```

Weitere Informationen finden Sie unter [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="delete-a-dial-in-conferencing-access-number"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen

Sie können eine Zugriffsnummer für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell löschen.
  
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-control-panel"></a>Löschen einer Zugriffsnummer für einwahlkonferenzen mithilfe von Skype Business Server-Systemsteuerung

1.  Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.
    
4. Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.
    
5. Klicken Sie anschließend auf **OK**.
    
### <a name="delete-a-dial-in-conferencing-access-number-by-using-skype-for-business-server-management-shell"></a>Löschen einer Zugriffsnummer für einwahlkonferenzen mithilfe von Skype für Business Server-Verwaltungsshell

Über **Remove-CsDialInConferencingAccessNumber** löschen Sie eine Einwahlnummer für Konferenzen.
  
Mit dem folgenden Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit der Identität „sip:RedmondDialInAccess@litwareinc.com“ gelöscht:
  
```
Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"
```

Mit dem folgenden Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region „Northwest“ zugeordnet sind:
  
```
Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber
```

Mit dem folgenden Befehl werden alle Zugriffsnummern für Einwahlkonferenzen mit der primären Sprache Italienisch gelöscht:
  
```
Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber
```

Weitere Informationen finden Sie unter [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/remove-csdialinconferencingaccessnumber?view=skype-ps).
  

