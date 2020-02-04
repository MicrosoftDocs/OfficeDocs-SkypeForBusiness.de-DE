---
title: 'Lync Server 2013: Konfigurieren der Voicemail-Escape-Konfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="8ef40-102">Konfigurieren von Voicemail-Escape in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef40-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ef40-103">_**Letztes Änderungsdatum des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8ef40-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8ef40-104">Wenn ein Benutzer das gleichzeitige Klingeln auf einem Mobiltelefon konfiguriert, wird ein Anrufer in der Regel an die persönliche Voicemail des Benutzers weitergeleitet, wenn das Mobiltelefon ausgeschaltet ist, der Akku nicht mehr zur verweilen oder außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="8ef40-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="8ef40-105">Mit lync Server 2013 können Benutzer entscheiden, dass unternehmensbezogene Anrufe an das Voicemailsystem des Unternehmens weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8ef40-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="8ef40-106">Insbesondere kann ein Zeitgeber konfiguriert werden, und wenn der Anruf von der Voicemail des Netzbetreibers innerhalb des definierten Zeitraums beantwortet wird, wird die Verbindung zwischen lync Server und dem Voicemailsystem des Netzbetreibers (und der persönlichen Voicemail des Benutzers) getrennt, während der verbleibende Benutzer Endpunkte im Unternehmenssystem Klingeln weiterhin.</span><span class="sxs-lookup"><span data-stu-id="8ef40-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="8ef40-107">Auf diese Weise wird der Anrufer automatisch an die Firmen-Voicemail des Benutzers weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8ef40-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="8ef40-108">Diese Konfiguration wird mit dem Cmdlet "lync Server-Verwaltungsshell", " **Satz-CsVoicePolicy**", auf der VoIP-Richtlinienebene mit den folgenden Parametern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ef40-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="8ef40-109">So konfigurieren Sie Voicemail Escape</span><span class="sxs-lookup"><span data-stu-id="8ef40-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="8ef40-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="8ef40-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8ef40-111">Geben Sie die folgenden Parameter für **Set-CsVoicePolicy** an:</span><span class="sxs-lookup"><span data-stu-id="8ef40-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="8ef40-112">**EnableVoicemailEscapeTimer**: Aktiviert oder deaktiviert den Escape-Timer.</span><span class="sxs-lookup"><span data-stu-id="8ef40-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="8ef40-p102">**PSTNVoicemailEscapeTimer**: Gibt den Timeoutwert in Millisekunden an. Der Standardwert lautet 1500 Millisekunden und der Wert kann zwischen 0 und 8000 Millisekunden liegen.</span><span class="sxs-lookup"><span data-stu-id="8ef40-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="8ef40-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ef40-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8ef40-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ef40-116">See Also</span></span>


[<span data-ttu-id="8ef40-117">Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ef40-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

