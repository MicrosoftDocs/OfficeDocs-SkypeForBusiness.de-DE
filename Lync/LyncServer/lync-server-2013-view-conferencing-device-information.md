---
title: 'Lync Server 2013: Anzeigen von Informationen zu Konferenz Geräten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5355ae418e53c44cc61340b57910993ac2afea2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a>Anzeigen von Informationen zu Konferenz Geräten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-20_

Mithilfe von Windows PowerShell und dem Cmdlet **Get-CsMeetingRoom** können Sie Informationen zu den Konferenz Geräten anzeigen, die für die Verwendung in Ihrer Organisation konfiguriert sind. Führen Sie das Cmdlet " **Get-CsMeetingRoom** " entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.

<div>


> [!NOTE]  
> Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.



</div>

Wenn Sie das Cmdlet " **Get-CsMeetingRoom** " ohne Parameter verwenden, gibt es Informationen zu allen Konferenz Geräten zurück. Optionale Parameter bieten verschiedene Möglichkeiten zum Filtern von Informationen. Ausführliche Informationen finden Sie im Abschnitt Parameters von [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>Anzeigen von Informationen zu allen Konferenz Geräten

  - Wenn Sie Details zu allen Konferenz Geräten anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsMeetingRoom
    
    Dieses Cmdlet gibt für jedes Konferenzgerät Informationen ähnlich der folgenden zurück. Beachten Sie, dass in diesem Beispiel nur einige der Informationen angezeigt werden, die angezeigt werden, wenn Sie dieses Cmdlet ausführen:
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a>Anzeigen von Informationen zu einem bestimmten Konferenzgerät

  - Wenn Sie Informationen zu einem bestimmten Konferenzgerät anzeigen möchten, schließen Sie den Parameter Identity gefolgt von der Identität des Konferenz Geräts ein (in der Regel der Name des Active Directory-Anzeigenamens). Beispiel:
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

