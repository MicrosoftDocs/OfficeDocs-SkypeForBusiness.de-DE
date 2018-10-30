---
title: 'Lync Server 2013: (Optional) Definieren von Geschäftszeiten für Reaktionsgruppen'
TOCTitle: (Optional) Definieren von Geschäftszeiten für Reaktionsgruppen
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205291(v=OCS.15)
ms:contentKeyID: 49295541
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Definieren von Geschäftszeiten für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

## Definieren von Geschäftszeiten

Mit der Einstellung der Geschäftszeiten wird definiert, wann der Workflow zur Anrufbeantwortung zur Verfügung steht, und es werden die Aktionen angegeben, die für Anrufe außerhalb der Geschäftszeiten ausgeführt werden sollen. Reaktionsgruppenadministratoren können mit dem **New-CsRgsHoursOfBusiness**-Cmdlet vordefinierte Zeitpläne erstellen, die Sie für eine beliebige Anzahl von Reaktionsgruppen verwenden können.


> [!TIP]
> Beim Erstellen oder Ändern eines Workflows können Sie einen benutzerdefinierten Zeitplan angeben, der nur für diesen Workflow gilt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Erstellen oder Ändern eines Workflows für Sammelanschlüsse in Lync Server 2013</A> oder <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013</A>.




> [!NOTE]
> Wenn ein Workflow als verwalteter Workflow definiert wird, kann jeder Benutzer, dem die Rolle CsResponseGroupManager zugewiesen ist, benutzerdefinierte Geschäftszeiten für die von ihnen verwalteten Workflows festlegen und ändern.




> [!IMPORTANT]
> Verwenden Sie das 24-Stunden-Format für die Parameter in den folgenden Cmdlets (z.&nbsp;B. 20:00=20&nbsp;Uhr).



## So erstellen Sie eine vordefinierte Geschäftszeitenauflistung

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie für jeden einzelnen Stundenbereich, den Sie definieren möchten, folgenden Befehl aus:
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Führen Sie zum Erstellen der Geschäftszeitenauflistung, welche die definierten Bereiche verwendet, folgenden Befehl aus:
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    Im folgenden Beispiel werden für Werktage die Geschäftszeiten von 9:00 Uhr bis 17:00 Uhr, für Samstage von 8:00 Uhr bis 10:00 Uhr und von 14:00 Uhr bis 18:00 Uhr und für Sonntage keine Geschäftszeiten festgelegt:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

## Siehe auch

#### Konzepte

[Erstellen oder Ändern eines Workflows für Sammelanschlüsse in Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Weitere Ressourcen

[New-CsRgsTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoursOfBusiness)

