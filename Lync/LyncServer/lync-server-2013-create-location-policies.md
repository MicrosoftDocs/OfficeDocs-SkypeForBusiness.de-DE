---
title: 'Lync Server 2013: Erstellen von ortungsrichtlinien'
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
ms.openlocfilehash: d99618d5221bb15d3e670a010c1894c69c17ed4d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532202"
---
# <a name="create-location-policies-in-lync-server-2013"></a>Erstellen von ortungsrichtlinien in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-11_

Lync Server verwendet eine ortungsrichtlinie, um lync-Clients während der Clientregistrierung für E9-1-1 zu aktivieren. Eine ortungsrichtlinie enthält die Einstellungen, mit denen die Implementierung von E9-1-1 definiert wird.

Sie können die globale ortungsrichtlinie bearbeiten und neue getaggte ortungsrichtlinien erstellen. Ein Client erhält eine globale Richtlinie, wenn er sich nicht in einem Subnetz mit einer zugeordneten ortungsrichtlinie befindet oder wenn dem Client keine Standortrichtlinie direkt zugewiesen wurde. Markierte Richtlinien werden Subnetzen oder Benutzern zugewiesen.

Um eine ortungsrichtlinie zu erstellen, müssen Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist oder Mitglied der Administratorrolle CsVoiceAdministrator ist oder gleichwertige Administratorrechte und-Berechtigungen aufweist.

Eine vollständige Beschreibung der Standortrichtlinien finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md). Cmdlets in diesem Verfahren verwenden eine ortungsrichtlinie, die mit den folgenden Werten definiert ist:


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
<td><p>Für Ihre Unternehmensrichtlinie müssen Sie einen Standort festlegen. Wenn Sie keinen Standort festlegen, können Sie von Notfalldiensten nicht in Notfällen gefunden werden. Legen Sie einen Speicherort fest.</p></td>
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
<td><p><strong>TwoWay</strong></p></td>
</tr>
<tr class="odd">
<td><p>LocationRefreshInterval</p></td>
<td><p><strong>2</strong></p></td>
</tr>
</tbody>
</table>


Ausführliche Informationen zum Arbeiten mit Standortrichtlinien finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:

  - New-CsLocationPolicy

  - Get-CsLocationPolicy

  - Set-CsLocationPolicy

  - Remove-CsLocationPolicy

  - Grant-CsLocationPolicy

<div>

## <a name="to-create-location-policies"></a>So erstellen Sie Standortrichtlinien

1.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.
    
    <div>
    

    > [!NOTE]  
    > CsLocationPolicy schlägt fehl, wenn die Einstellung für <STRONG>PstnUsage</STRONG> nicht bereits in der globalen Liste der PstnUsages.

    
    </div>

2.  Führen Sie optional das folgende Cmdlet aus, um die globale ortungsrichtlinie zu bearbeiten:
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  Führen Sie die folgenden Schritte aus, um eine getaggte ortungsrichtlinie zu erstellen.
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte getagged-ortungsrichtlinie auf eine Benutzerrichtlinie anzuwenden.
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

