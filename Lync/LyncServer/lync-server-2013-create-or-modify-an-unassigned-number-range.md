---
title: 'Lync Server 2013: Erstellen oder Ändern eines nicht zugewiesenen Nummernbereichs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Erstellen oder Ändern eines nicht zugewiesenen Nummernbereichs in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren, um nicht zugewiesene Nummernbereiche für die Ankündigungs Anwendung zu konfigurieren.

<div>


> [!IMPORTANT]  
> Bevor Sie die Tabelle nicht zugewiesene Nummern konfigurieren, müssen Sie bereits eine oder mehrere Ankündigungen definiert haben oder eine automatische UM-Telefonzentrale (Unified Messaging) von Exchange einrichten.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>So verwenden Sie die lync Server-Systemsteuerung, um nicht zugewiesene Telefonnummern zu konfigurieren

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und klicken Sie dann auf **Nicht zugewiesene Nummer**.

4.  Führen Sie auf der Seite **Nicht zugewiesene Nummer** eine der folgenden Aktionen aus:
    
      - Wenn Sie einen neuen Nummernbereich erstellen möchten, klicken Sie auf **Neu**. Geben Sie unter **Name** den Namen für diesen Nummernbereich ein.
        
        <div>
        

        > [!NOTE]  
        > Nachdem Sie den neuen Bereich nicht zugewiesener Nummern per Commit in die Datenbank übernommen haben, können Sie diesen Namen nicht mehr ändern.

        
        </div>
    
      - Wenn Sie einen vorhandenen Nummernbereich ändern möchten, geben Sie im Suchfeld den gesamten Namen oder einen Teil des Namens für den Nummernbereich ein. Klicken Sie in der Ergebnisliste der Nummernbereiche auf den gewünschten Namen, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.

5.  Geben Sie im ersten Feld **Nummernbereich** die Startnummer für den Bereich ein und geben Sie dann im zweiten Feld **Nummernbereich** die letzte Nummer für den Bereich ein.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Die Startnummer für den Bereich muss kleiner oder gleich der Endnummer sein.</P>
    > <LI>
    > <P>Wenn die erste Nummer im Bereich oder die letzte Nummer im Bereich eine Durchwahl umfassen, müssen sowohl die erste als auch die letzte Nummer im Bereich einen Durchwahl aufweisen und die Durchwahlnummer muss für die erste und die letzte Nummer übereinstimmen.</P>
    > <LI>
    > <P>Die Nummer muss mit dem regulären Ausdruck übereinstimmen (Tel:)? ( \+)? [1-9] \d{0,17}(; ext = [1-9] \d{0,9})? Demnach kann die Nummer mit der Zeichenfolge „tel:“ (wenn Sie diese Zeichenfolge nicht angeben, wird sie automatisch hinzugefügt) sowie einem Pluszeichen (+) und einer Zahl zwischen 1 und 9 beginnen. Die Telefonnummer kann bis zu 17 Zeichen umfassen, gefolgt von einer Durchwahl im Format „;ext=“ plus der Durchwahlnummer.</P></LI></UL>

    
    </div>

6.  Führen Sie im Abschnitt **Ansagedienst** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Ansage**.
    
      - Klicken Sie auf **Exchange UM**.

7.  Wenn Sie im vorherigen Schritt auf **Ansage** geklickt haben, führen Sie eine der folgenden Aktionen aus:
    
    1.  Klicken Sie unter **FQDN des Zielservers**auf **auswählen**, klicken Sie auf die Dienst-ID des Anwendungsdiensts, der die Ankündigungs Anwendung ausführt, die eingehende Anrufe an diesen Bereich nicht zugewiesener Nummern abwickeln soll, und klicken Sie dann auf **OK**.
    
    2.  Klicken Sie im Abschnitt **Ansage** auf die Ansage, die für diesen Bereich nicht zugewiesener Nummern wiedergegeben werden soll.

8.  Wenn Sie im vorherigen Schritt auf **Exchange UM** geklickt haben, klicken Sie unter **Nummer der automatischen Telefonzentrale** auf **Auswählen**, klicken Sie auf die für diesen Bereich nicht zugewiesener Nummern zu verwendende Telefonnummer und klicken Sie dann auf **OK**.

9.  Klicken Sie anschließend auf **OK**.

10. Stellen Sie sicher, dass die Bereiche nicht zugewiesener Nummern auf der Seite **Nicht zugewiesene Nummer** in der gewünschten Reihenfolge angezeigt werden. Wenn Sie die Position eines Bereichs in der Tabelle ändern möchten, klicken Sie auf einen oder mehrere aufeinanderfolgende Namen in der Liste der Bereiche und klicken Sie anschließend auf den Aufwärts- oder Abwärtspfeil.
    
    <div>
    

    > [!TIP]  
    > Lync Server durchsucht die Tabelle nicht zugewiesene Nummern von oben nach unten und verwendet den ersten Bereich, der der nicht zugewiesenen Zahl entspricht. Wenn sich Bereiche überlappen und auf einen Bereich als letzte Aktion zurückgegriffen werden soll, stellen Sie sicher, dass sich dieser Bereich ganz unten in der Liste befindet.

    
    </div>

11. Wenn Sie die Bereiche nicht zugewiesener Nummern in der gewünschten Reihenfolge angeordnet haben, klicken Sie auf **Commit für alle**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>So verwenden Sie Windows PowerShell zum Konfigurieren von nicht zugewiesenen Telefonnummern

1.  Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie **New-CsUnassignedNumber** zum Erstellen eines neuen Bereichs nicht zugewiesener Nummern. Verwenden Sie **Set-CsUnassignedNumber** zum Ändern eines vorhandenen Bereichs nicht zugewiesener Nummern.
    
    <div>
    

    > [!TIP]  
    > Wenn sich Bereiche überlappen und die Bereiche in einer bestimmten Reihenfolge angewendet werden sollen, fügen Sie den Parameter „Priority“ ein. Daraufhin wird der Bereich mit der höchsten Priorität für den Anruf angewendet.

    
    </div>
    
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

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Löschen eines nicht zugewiesenen Nummernbereichs in lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

