---
title: Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a102b226-0460-4d5c-82f9-79b8444fa958
description: Erstellen, Ändern oder Löschen nicht zugewiesener Nummernbereiche für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich darauf aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.
ms.openlocfilehash: dcdf8fe1bf4d087b27723626ccd9207df14238c4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856312"
---
# <a name="create-or-modify-an-unassigned-number-range-in-skype-for-business-server"></a>Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Skype for Business Server
 
Erstellen, Ändern oder Löschen nicht zugewiesener Nummernbereiche für die Ankündigungsanwendung in Skype for Business Server Enterprise-VoIP. Dies wirkt sich darauf aus, wie Anrufe an nicht zugewiesene Nummern verarbeitet werden.
  
mit Skype for Business Server können Sie sagen, was mit eingehenden Anrufen an Telefonnummern geschieht, die für Ihre Organisation gültig sind, aber keinem Benutzer oder einem Telefon zugewiesen sind. Um solche Anrufe zu verarbeiten, richten Sie eine Tabelle nicht zugewiesener Nummern ein. Sie können die Tabelle verwenden, um die Anrufe an eine Ankündigungsanwendung oder an einen Exchange UM-Server weiterzuleiten.
  
Wie Sie die Tabelle nicht zugewiesener Rufnummern konfigurieren, richtet sich danach, wie Sie diese verwenden möchten. Sie können die Tabelle mit allen gültigen Erweiterungen für Ihre Organisation, nur mit nicht zugewiesenen Erweiterungen oder mit einer Kombination aus beiden Nummerntypen konfigurieren. Die Tabelle nicht zugewiesener Nummern kann sowohl zugewiesene als auch nicht zugewiesene Nummern enthalten, wird jedoch nur aufgerufen, wenn ein Anrufer eine Nummer wählt, die derzeit nicht zugewiesen ist. Wenn Sie alle gültigen Erweiterungen in die Tabelle nicht zugewiesener Nummern einschließen, können Sie die Aktion angeben, die ausgeführt wird, wenn jemand Ihre Organisation verlässt, ohne die Tabelle neu konfigurieren zu müssen. Wenn Sie nicht zugewiesene Erweiterungen in die Tabelle aufnehmen, können Sie die Aktion ändern, die für bestimmte Zahlen ausgeführt wird. Wenn Sie beispielsweise die Erweiterung für Ihren Kundendienst ändern, können Sie die alte Kundendienstnummer in die Tabelle aufnehmen und sie dann einer Ankündigung zuweisen, die die neue Nummer bereitstellt.
  
## <a name="configure-unassigned-phone-numbers"></a>Konfigurieren nicht zugewiesener Telefonnummern

Verwenden Sie eines der folgenden Verfahren, um bereiche nicht zugewiesener Nummern für die Ankündigungsanwendung zu konfigurieren.
  
> [!IMPORTANT]
> Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, muss in Ihrem System entweder ankündigungsdefiniert oder eine Exchange automatische Um-Telefonzentrale (Unified Messaging) eingerichtet sein. 
  
> [!TIP]
> Wenn jemand eine nicht zugewiesene Nummer aufruft, durchsucht Skype for Business Server die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten übereinstimmenden Bereich. Daher sollte eine Aktion, die als letzte Möglichkeit ausgeführt werden soll, für den letzten Bereich in der Tabelle angegeben werden. 
  
### <a name="to-use-skype-for-business-server-control-panel-to-configure-unassigned-phone-numbers"></a>So verwenden Sie Skype for Business Server Systemsteuerung, um nicht zugewiesene Telefonnummern zu konfigurieren

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen**, und klicken Sie dann auf **Nicht zugewiesene Nummer**.
    
4. Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:
    
   - Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu**. Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.
    
     > [!NOTE]
     > Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern. 
  
   - Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.
    
5. Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein, und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    
   - Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.
    
   - Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen, und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.
    
   - Die Zahl muss mit dem regulären Ausdruck `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` übereinstimmen. Dies bedeutet, dass die Zahl möglicherweise mit der Zeichenfolge beginnt `tel:` (wenn Sie diese Zeichenfolge nicht angeben, wird sie automatisch für Sie hinzugefügt), ein Pluszeichen (+) und eine Ziffer 1 bis 9. Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.
    
6. Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus: 
    
   - Klicken Sie auf **Ansage**.
    
   - Klicken Sie auf **Exchange UM**.
    
7. Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:
    
    a. Klicken Sie unter **FQDN des Zielservers** auf **Auswählen**, klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die Ansageanwendung ausführt, die eingehende Anrufe für diesen Bereich nicht zugewiesener Nummern verarbeitet, und klicken Sie dann auf **OK**.
    
    b. Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.
    
8. Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen**, klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer, und klicken Sie dann auf **OK**.
    
9. Klicken Sie auf **OK**.
    
10. Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche, und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.
    
    > [!TIP]
    > Skype for Business Server durchsucht die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Nummer entspricht. Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet. 
  
11. Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-configure-unassigned-phone-numbers"></a>So verwenden Sie Skype for Business Server Verwaltungsshell zum Konfigurieren nicht zugewiesener Telefonnummern

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Verwenden Sie **New-CsUnassignedNumber** zum Erstellen eines neuen Bereichs nicht zugewiesener Nummern. Verwenden Sie **Set-CsUnassignedNumber** zum Ändern eines vorhandenen Bereichs nicht zugewiesener Nummern.
    
    > [!TIP]
    > Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter "Priority" ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet. Der Wert 0 stellt die höchste Priorität dar.
  
    Führen Sie in der Befehlszeile eine der folgenden Aktionen aus:
    
   - Führen Sie zum Erstellen eines Nummernbereichs für einen Ankündigungsdienst Folgendes aus:
    
     ```powershell
     New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
     ```

   - Oder führen Sie zum Erstellen eines Nummernbereichs für die automatische Exchange UM-Telefonzentrale Folgendes aus:
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
     ```

     Beispiel:
    
     ```powershell
     New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
     ```

     Oder
    
     ```powershell
     New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
     ```

     Im folgenden Beispiel wird veranschaulicht, wie Sie die Nummern in einem vorhandenen Bereich nicht zugewiesener Nummern ändern:
    
     ```powershell
     Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"
     ```

## <a name="delete-an-unnasigned-number-range"></a>Löschen eines Bereichs nicht signierter Nummern

### <a name="to-use-skype-for-business-server-control-panel-to-delete-an-unassigned-number-range"></a>So verwenden Sie Skype for Business Server Systemsteuerung, um einen Bereich nicht zugewiesener Nummern zu löschen

1.  Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Nicht zugewiesene Nummer**.
    
4. Geben Sie auf der Seite **"Nicht zugewiesene Zahl"** im Suchfeld den Namen des bereichs nicht zugewiesener Nummern, den Sie löschen möchten, ganz oder teilweise ein.
    
5. Klicken Sie in der resultierenden Liste der Nummernbereiche auf den Namen, klicken Sie auf **"Bearbeiten"** und dann auf **"Löschen".**
    
6. Klicken Sie auf **"Commit für alle** ausführen".
    
### <a name="to-use-skype-for-business-server-management-shell-to-delete-an-unassigned-number-range"></a>So verwenden Sie Skype for Business Server Verwaltungsshell, um einen Bereich nicht zugewiesener Nummern zu löschen

1. Melden Sie sich bei dem Computer an, auf dem Skype for Business Server Verwaltungsshell als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten installiert ist, wie unter **"Stellvertretungs-Setupberechtigungen"** beschrieben.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Geben Sie in die Befehlszeile Folgendes ein:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
   ```

    Beispiel:
    
   ```powershell
   Remove-CsUnassignedNumber -Identity "Unassigned range 1"
   ```

    > [!NOTE]
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter [Remove-CsCallParkOrbit](/powershell/module/skype/remove-cscallparkorbit?view=skype-ps). 
  
## <a name="see-also"></a>Siehe auch

[New-CsUnassignedNumber](/powershell/module/skype/new-csunassignednumber?view=skype-ps)
  
[Set-CsUnassignedNumber](/powershell/module/skype/set-csunassignednumber?view=skype-ps)
  
[Get-CsUnassignedNumber](/powershell/module/skype/get-csunassignednumber?view=skype-ps)