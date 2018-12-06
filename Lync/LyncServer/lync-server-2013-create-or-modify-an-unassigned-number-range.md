---
title: 'Lync Server 2013: Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern'
TOCTitle: Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412748(v=OCS.15)
ms:contentKeyID: 49294937
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren zum Konfigurieren nicht zugewiesener Nummernbereiche für die Ansageanwendung.


> [!IMPORTANT]
> Bevor Sie die Tabelle nicht zugewiesener Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ansagen definiert oder eine automatische Exchange Unified Messaging-Telefonzentrale (UM) eingerichtet haben.



## So verwenden Sie die Lync Server-Systemsteuerung zum Konfigurieren nicht zugewiesener Telefonnummern

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** , und klicken Sie dann auf **Nicht zugewiesene Nummer** .

4.  Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:
    
      - Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu** . Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.
        

        > [!NOTE]
        > Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern.

    
      - Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten** , und klicken Sie dann auf **Details anzeigen** .

5.  Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein, und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    

    > [!NOTE]
    > <UL>
    > <LI>
    > <P>Die Startnummer für den Bereich muss kleiner oder gleich der letzten Nummer im Bereich sein.</P>
    > <LI>
    > <P>Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen, und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</P>
    > <LI>
    > <P>Die Nummer muss mit dem regulären Ausdruck "(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?" übereinstimmen. Demnach kann die Nummer mit der Zeichenfolge "tel:" (wenn Sie diese Zeichenfolge nicht angeben, wird sie automatisch hinzugefügt) sowie einem Pluszeichen (+) und einer Zahl zwischen&nbsp;1 und&nbsp;9 beginnen. Die Telefonnummer kann bis zu 17&nbsp;Zeichen umfassen, gefolgt von einer Durchwahl im Format ";ext=" plus der Durchwahlnummer.</P></LI></UL>



6.  Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Ansage** .
    
      - Klicken Sie auf **Exchange UM** .

7.  Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:
    
    1.  Klicken Sie unter **FQDN des Zielservers** auf **Auswählen** , klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die Ansageanwendung zur Verarbeitung eingehender Anrufe für diesen Bereich nicht zugewiesener Nummern ausführt, und klicken Sie dann auf **OK** .
    
    2.  Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.

8.  Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen** , klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer, und klicken Sie dann auf **OK** .

9.  Klicken Sie auf **OK** .

10. Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche, und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.
    

    > [!TIP]
    > Lync Server durchsucht die Tabelle nicht zugewiesener Nummern von oben nach unten und verwendet den ersten Bereich, der mit der nicht zugewiesenen Nummer übereinstimmt. Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet.



11. Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle** .

## So verwenden Sie die Windows PowerShell zum Konfigurieren nicht zugewiesener Telefonnummern

1.  Melden Sie sich auf dem Computer, auf dem die Lync Server-Verwaltungsshell installiert ist, als Mitglied der Gruppe "RTCUniversalServerAdmins" oder mit den erforderlichen Benutzerrechten an, wie beschrieben unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsUnassignedNumber**zum Erstellen eines neuen Bereichs nicht zugewiesener Nummern. Verwenden Sie **Set-CsUnassignedNumber** zum Ändern eines vorhandenen Bereichs nicht zugewiesener Nummern.
    

    > [!TIP]
    > Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter "Priority" ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet.

    
    Führen Sie in der Befehlszeile eine der folgenden Aktionen aus:
    
      - Führen Sie zum Erstellen eines Nummernbereichs für einen Ankündigungsdienst Folgendes aus:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Oder führen Sie zum Erstellen eines Nummernbereichs für die automatische Exchange UM-Telefonzentrale Folgendes aus:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Beispiel:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Oder
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    Im folgenden Beispiel wird veranschaulicht, wie Sie die Nummern in einem vorhandenen Bereich nicht zugewiesener Nummern ändern:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## Siehe auch

#### Aufgaben

[Löschen eines Bereichs nicht zugewiesener Nummern](lync-server-2013-delete-an-unassigned-number-range.md)  

#### Weitere Ressourcen

[New-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

