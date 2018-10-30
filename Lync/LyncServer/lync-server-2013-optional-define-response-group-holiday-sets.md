---
title: (Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013
TOCTitle: (Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49890755
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (Optional) Definieren von Feiertagsschemas für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.


> [!NOTE]
> Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten.



## So erstellen Sie einen Feiertagssatz

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl für jeden Feiertag aus, den Sie definieren möchten:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Führen Sie den folgenden Befehl aus, um einen Feiertagssatz mit den von Ihnen definierten Feiertagen zu erstellen:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    Das folgende Beispiel enthält einen Feiertagssatz mit zwei Feiertagen:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

## Siehe auch

#### Konzepte

[Erstellen oder Ändern eines Workflows für Sammelanschlüsse in Lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### Weitere Ressourcen

[New-CsRgsHoliday](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHolidaySet)

