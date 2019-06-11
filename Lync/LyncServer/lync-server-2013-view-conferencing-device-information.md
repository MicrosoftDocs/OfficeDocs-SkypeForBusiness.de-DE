---
title: 'Lync Server 2013: Anzeigen von Informationen zu Konferenz Geräten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4b40e0ee28f13aa6be52009b750258c5cdadffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="3c1e8-102">Anzeigen von Informationen zu Konferenz Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c1e8-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c1e8-103">_**Letztes Änderungsdatum des Themas:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3c1e8-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3c1e8-104">Mithilfe von Windows PowerShell und dem Cmdlet **Get-CsMeetingRoom** können Sie Informationen zu den Konferenz Geräten anzeigen, die für die Verwendung in Ihrer Organisation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="3c1e8-105">Führen Sie das Cmdlet " **Get-CsMeetingRoom** " entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c1e8-106">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="3c1e8-107">Wenn Sie das Cmdlet " **Get-CsMeetingRoom** " ohne Parameter verwenden, gibt es Informationen zu allen Konferenz Geräten zurück.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="3c1e8-108">Optionale Parameter bieten verschiedene Möglichkeiten zum Filtern von Informationen.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="3c1e8-109">Ausführliche Informationen finden Sie im Abschnitt Parameters von [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="3c1e8-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="3c1e8-110">Anzeigen von Informationen zu allen Konferenz Geräten</span><span class="sxs-lookup"><span data-stu-id="3c1e8-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="3c1e8-111">Wenn Sie Details zu allen Konferenz Geräten anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3c1e8-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="3c1e8-112">Dieses Cmdlet gibt für jedes Konferenzgerät Informationen ähnlich der folgenden zurück.</span><span class="sxs-lookup"><span data-stu-id="3c1e8-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="3c1e8-113">Beachten Sie, dass in diesem Beispiel nur einige der Informationen angezeigt werden, die angezeigt werden, wenn Sie dieses Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="3c1e8-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="3c1e8-114">Anzeigen von Informationen zu einem bestimmten Konferenzgerät</span><span class="sxs-lookup"><span data-stu-id="3c1e8-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="3c1e8-115">Wenn Sie Informationen zu einem bestimmten Konferenzgerät anzeigen möchten, schließen Sie den Parameter Identity gefolgt von der Identität des Konferenz Geräts ein (in der Regel der Name des Active Directory-Anzeigenamens).</span><span class="sxs-lookup"><span data-stu-id="3c1e8-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="3c1e8-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="3c1e8-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="3c1e8-117">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="3c1e8-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

