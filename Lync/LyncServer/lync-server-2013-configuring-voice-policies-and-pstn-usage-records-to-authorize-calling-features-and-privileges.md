---
title: 'Lync Server 2013: Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice policies and PSTN usage records to authorize calling features and privileges
ms:assetid: 63f22010-a3d7-4cbd-86e8-6fc0e13c2b84
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398450(v=OCS.15)
ms:contentKeyID: 48184307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b9f7da3f8560ae0a897211405d686d9ed35101e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges-in-lync-server-2013"></a><span data-ttu-id="643c5-102">Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und -berechtigungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="643c5-102">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="643c5-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="643c5-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="643c5-104">Eine *VoIP-Richtlinie* ermöglicht eine Reihe von Anruffunktionen und ordnet einen oder mehrere PSTN-Verwendungsdaten Sätze an, um die Anruffeatures und Berechtigungen von Benutzern zu definieren, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="643c5-104">A *voice policy* enables a set of calling features and associates one or more PSTN usage records to define the calling features and permissions of users who are assigned the policy.</span></span>

<span data-ttu-id="643c5-105">Der VoIP-Richtlinienbereich kann entweder ein *Standort* sein (der die Standardfeatures und-Berechtigungen für eine Netzwerk Website definiert) oder ein *Benutzer* (der die Features und Berechtigungen definiert, die für einzelne Benutzer oder Gruppen zugewiesen werden sollen).</span><span class="sxs-lookup"><span data-stu-id="643c5-105">Voice policy scope can be either *Site* (which defines the default features and permissions for a network site) or *User* (which defines the features and permissions to be assigned on a per-user or group basis).</span></span> <span data-ttu-id="643c5-106">Benutzer, denen keine VoIP-Richtlinie zugewiesen ist, werden automatisch der globalen Richtlinie zugewiesen, bei der es sich um die Standard VoIP-Richtlinie handelt, die mit dem Produkt installiert wird.</span><span class="sxs-lookup"><span data-stu-id="643c5-106">Users not assigned to a voice policy will automatically be assigned to the global policy, which is the default voice policy that is installed with the product.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="643c5-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-voice-policies.md">VoIP-Richtlinien in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="643c5-107">For details, see <A href="lync-server-2013-voice-policies.md">Voice policies in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="643c5-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="643c5-108">In This Section</span></span>

  - [<span data-ttu-id="643c5-109">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="643c5-109">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="643c5-110">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="643c5-110">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)

  - [<span data-ttu-id="643c5-111">Konfigurieren von Voicemail-Escape in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="643c5-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

