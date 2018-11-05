---
title: 'Lync Server 2013: Sicherstellen, dass Wählplänen Regionen zugewiesen wurden'
TOCTitle: Sicherstellen, dass Wählplänen Regionen zugewiesen wurden
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425903(v=OCS.15)
ms:contentKeyID: 49293765
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sicherstellen, dass Wählplänen in Lync Server 2013 Regionen zugewiesen wurden

 

_**Letztes Änderungsdatum des Themas:** 2010-11-02_

Wähleinstellungen, die für Einwahlkonferenzen verwendet werden, müssen eine **Region für Einwahlkonferenzen** enthalten, um Zugriffsnummern für Einwahlkonferenzen den entsprechenden Wähleinstellungen zuzuordnen. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.

Da es wichtig ist, eine Region für alle Wähleinstellungen anzugeben, wird empfohlen, mit diesem Verfahren das Vorhandensein von Regionen für alle Wähleinstellungen zu überprüfen. Dieser Schritt ist optional.

Verwenden Sie das **Get-CsDialPlan**-Cmdlet, um zu überprüfen, ob die Region für alle Wählpläne für Einwahlkonferenzen festgelegt wurde. Wenn die Region in bestimmten Wählplänen nicht vorhanden ist, können Sie die Region über das **Set-CsDialPlan**-Cmdlet festlegen. Alternativ können Sie die Region bei vorhandenen Wählplänen auch in der Lync Server-Systemsteuerung ändern. Genaue Informationen zur Verwendung der Lync Server-Systemsteuerung finden Sie unter [Ändern eines Wählplans in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

## So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator** , **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Beispiel:
    
        Get-CsDialPlan
    
    In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.

4.  Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

## So legen Sie die Region für einen Satz mit Wähleinstellungen fest

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator** , **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Beispiel:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

