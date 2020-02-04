---
title: 'Lync Server 2013: Erstellen von Standortrichtlinien'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c10244bb3a70f7218dc3967e7f4f134048024f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-location-policies-in-lync-server-2013"></a>Erstellen von Standortrichtlinien in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-11_

Lync Server verwendet eine ortungsrichtlinie, um lync-Clients für E9-1-1 während der Clientregistrierung zu aktivieren. Eine Standortrichtlinie enthält die Einstellungen für die Definition der Notrufdienstimplementierung.

Sie können die globale Standortrichtlinie bearbeiten und bereichsspezifische Standortrichtlinien erstellen. Ein Client, der sich nicht in einem Subnetz mit zugeordneter Standortrichtlinie befindet oder dem nicht direkt eine Standortrichtlinie zugeordnet wurde, ruft eine globale Richtlinie ab. Bereichsspezifische Standortrichtlinien werden Subnetzen oder Benutzern zugewiesen.  

Zum Erstellen einer Standortrichtlinie müssen Sie ein Konto verwenden, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist oder entsprechende Administratorrechte und -berechtigungen besitzt.

Eine vollständige Beschreibung der Standortrichtlinien finden Sie unter [Definieren der Standortrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md). Cmdlets in diesem Verfahren verwenden eine Standortrichtlinie, die mit den folgenden Werten definiert ist:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
<th>Wert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnhancedEmergencyServicesEnabled</p></td>
<td><p><strong>True</strong></p></td>
</tr>
<tr class="even">
<td><p>LocationRequired</p></td>
<td><p><strong>Haftungsausschluss</strong></p></td>
</tr>
<tr class="odd">
<td><p>EnhancedEmergencyServiceDisclaimer</p></td>
<td><p>Die Unternehmensrichtlinie erfordert, dass Sie einen Standort festlegen. Wenn Sie keinen Standort festlegen, können Sie im Ernstfall nicht von Notfalldiensten lokalisiert werden. Bitte legen Sie einen Standort fest.</p></td>
</tr>
<tr class="even">
<td><p>UseLocationForE911Only</p></td>
<td><p><strong>False</strong></p></td>
</tr>
<tr class="odd">
<td><p>PstnUsage</p></td>
<td><p><strong>EmergencyUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>EmergencyDialString</p></td>
<td><p><strong>911</strong></p></td>
</tr>
<tr class="odd">
<td><p>EmergencyDialMask</p></td>
<td><p><strong>112</strong></p></td>
</tr>
<tr class="even">
<td><p>NotificationUri</p></td>
<td><p><strong>sip:security@litwareinc.com</strong></p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUri</p></td>
<td><p><strong>sip:+14255550123@litwareinc.com</strong></p></td>
</tr>
<tr class="even">
<td><p>ConferenceMode</p></td>
<td><p><strong>twoway</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Details zum Arbeiten mit Standortrichtlinien finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>So erstellen Sie Standortrichtlinien

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    <div>
    

    > [!NOTE]  
    > Bei Ausführung von „CsLocationPolicy“ tritt ein Fehler auf, wenn sich die Einstellung für <STRONG>PstnUsage</STRONG> nicht bereits in der globalen Liste „PstnUsages“ befindet.

    
    </div>

2.  Optional können Sie auch das folgende Cmdlet ausführen, um die globale Standortrichtlinie zu bearbeiten:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Führen Sie folgendes Cmdlet aus, um eine bereichsspezifische Standortrichtlinie zu erstellen.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte bereichsspezifische Standortrichtlinie auf eine Benutzerrichtlinie anzuwenden.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

