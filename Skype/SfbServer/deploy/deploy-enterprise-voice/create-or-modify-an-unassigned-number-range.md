---
title: Erstellen Sie oder ändern Sie einen Bereichs nicht zugewiesenen Nummern in Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Erstellen Sie, ändern Sie oder löschen Sie nicht zugewiesener Nummernbereiche für ansageanwendung in Skype für Business Server Enterprise-VoIP. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.
ms.openlocfilehash: 9546e4caaab30ae7582866dbcefd680b04de33f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223191"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Erstellen Sie oder ändern Sie einen Bereichs nicht zugewiesenen Nummern in Skype für Business Server
 
Erstellen Sie, ändern Sie oder löschen Sie nicht zugewiesener Nummernbereiche für ansageanwendung in Skype für Business Server Enterprise-VoIP. Dies wirkt sich auf den Umgang mit Anrufen an nicht zugewiesene Nummern aus.
  
Skype für Business Server können Sie sagen, was geschieht, um eingehende Anrufe an externe Telefonnummern, die für Ihre Organisation gültig sind, aber nicht für einen Benutzer oder ein Telefon zugewiesen sind. Zum Abwickeln solcher Anrufe richten Sie eine Tabelle mit nicht zugewiesenen Nummern ein. Die Tabelle können die Anrufe an eine ankündigungsanwendung oder mit einem Exchange UM-Server weitergeleitet.
  
Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Durchwahlnummern für Ihre Organisation konfigurieren, nur mit nicht zugewiesenen Durchwahlnummern oder als eine Kombination beider Nummerntypen. Die Tabelle nicht zugewiesener Rufnummern kann sowohl zugewiesene als auch nicht zugewiesene Rufnummern enthalten, wird jedoch nur ausgelöst, wenn ein Anrufer eine derzeit nicht zugewiesene Rufnummer wählt. Wenn Sie alle gültigen Durchwahlnummern in die Tabelle nicht zugewiesener Nummern aufnehmen, können Sie eine Aktion angeben, die bei Ausscheiden eines Mitarbeiters aus der Organisation ausgeführt werden soll. In diesem Fall ist eine Neukonfiguration der Tabelle nicht erforderlich. Wenn Sie nicht zugewiesene Durchwahlnummern in die Tabelle aufnehmen, können Sie die Aktion anpassen, die für bestimmte Nummern ausgeführt wird. Wenn Sie beispielsweise die Durchwahlnummer für Ihren Kundendienst ändern, können Sie die alte Rufnummer des Kundendiensts in die Tabelle aufnehmen und ihr dann eine Ansage zuweisen, in der die neue Rufnummer bereitgestellt wird.
  
## <a name="configure-unassigned-phone-numbers"></a>Konfigurieren von nicht zugewiesenen Telefonnummern

Verwenden Sie eines der folgenden Verfahren zum Konfigurieren nicht zugewiesener Nummernbereiche für die Ankündigung an.
  
> [!IMPORTANT]
> Bevor Sie den Tabelle mit nicht zugewiesenen Nummern konfigurieren, muss Ihr System müssen bereits Ansagen definiert oder eine automatische Telefonzentrale von Exchange Unified Messaging (UM) eingerichtet. 
  
> [!TIP]
> Wenn Sie angerufen werden eine nicht zugewiesene Nummer, Skype für Business Server durchsucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich. Sie sollten also als letzte Lösungsmöglichkeit eine Aktion definieren, die für den letzten Bereich in der Tabelle ausgeführt werden soll. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>Mit der Skype Business Server-Systemsteuerung konfigurieren nicht zugewiesener Telefonnummern

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und klicken Sie dann auf **Nicht zugewiesene Nummer**.
    
4. Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:
    
   - Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu**. Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.
    
     > [!NOTE]
     > Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern. 
  
   - Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.
    
5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    
   - Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.
    
   - Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.
    
   - Die Anzahl muss mit den regulären Ausdruck übereinstimmen (tel:) ? (\+) [1-9] ? \d{0,17}(; Ext = [1-9] \d{0,9}) ?. Dies bedeutet, dass die Anzahl beginnt mit der Zeichenfolge tel: (Wenn Sie diese Zeichenfolge nicht angeben, es wird automatisch hinzugefügt werden für Sie), ein Pluszeichen (+) sowie ein Zahl von 1 bis 9. Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format „;ext=“ plus der Durchwahlnummer.
    
6. Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus: 
    
   - Klicken Sie auf **Ansage**.
    
   - Klicken Sie auf **Exchange UM**.
    
7. Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:
    
    a. Klicken Sie unter **FQDN des Zielservers**klicken Sie auf **auswählen**, klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die ankündigungsanwendung ausgeführt, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern behandelt werden sollen wird, und klicken Sie dann auf **OK**.
    
    b. Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.
    
8. Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen**, klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer und klicken Sie dann auf **OK**.
    
9. Klicken Sie anschließend auf **OK**.
    
10. Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.
    
    > [!TIP]
    > Skype für Business Server sucht den Tabelle nicht zugewiesenen Nummern von oben nach unten und verwendet den ersten Bereich, der nicht zugewiesene Nummer entspricht. Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet. 
  
11. Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>Skype für Business Server-Verwaltungsshell verwenden, zum Konfigurieren nicht zugewiesener Telefonnummern

1. Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Verwenden Sie **New-CsUnassignedNumber** zum Erstellen eines neuen Bereichs nicht zugewiesener Nummern. Verwenden Sie **Set-CsUnassignedNumber** zum Ändern eines vorhandenen Bereichs nicht zugewiesener Nummern.
    
    > [!TIP]
    > Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter „Priority“ ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet. Der Wert 0 gibt die höchste Priorität.
  
    Führen Sie in der Befehlszeile eine der folgenden Aktionen aus:
    
   - Führen Sie zum Erstellen eines Nummernbereichs für einen Ankündigungsdienst Folgendes aus:
    
     ```
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Oder führen Sie zum Erstellen eines Nummernbereichs für die automatische Exchange UM-Telefonzentrale Folgendes aus:
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Beispiel:
    
     ```
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Oder
    
     ```
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     Im folgenden Beispiel wird veranschaulicht, wie Sie die Nummern in einem vorhandenen Bereich nicht zugewiesener Nummern ändern:
    
     ```
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Löschen eines Bereichs nicht zugewiesener Nummern

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>Skype Business Server-Systemsteuerung verwenden, um einen nicht zugewiesenen Nummern zu löschen

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und klicken Sie dann auf **Nicht zugewiesene Nummer**.
    
4. Geben Sie auf der Seite **Nicht zugewiesene Nummer** im Suchfeld Teile oder den vollständigen Namen des Bereichs nicht zugewiesener Nummern ein, den Sie löschen möchten.
    
5. Klicken Sie in der resultierenden Liste der Nummernbereiche auf den Namen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Löschen**.
    
6. Klicken Sie auf **Commit für alle**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>Skype für Business Server-Verwaltungsshell verwenden, um einen nicht zugewiesenen Nummern zu löschen

1. Melden Sie sich an dem Computer, auf dem Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe RTCUniversalServerAdmins oder mit den erforderlichen Benutzerrechten installiert ist wie beschrieben unter **Delegate Setup Permissions**.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Geben Sie in der Befehlszeile Folgendes ein:
    
   ```
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Beispiel:
    
   ```
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter [Remove-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Siehe auch

[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/get-csunassignednumber?view=skype-ps)
