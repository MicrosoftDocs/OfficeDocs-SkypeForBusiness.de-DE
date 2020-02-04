---
title: 'Lync Server 2013: Bereitstellen des Lync VDI-Plug-Ins'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d51b1858e3e1944d290d907ee14691786bf3cc53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="9c5a3-102">Bereitstellen des Lync VDI-Plug-Ins in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c5a3-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c5a3-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9c5a3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9c5a3-104">Der lync 2013-Client unterstützt Audio und Video in einer VDI-Umgebung (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="9c5a3-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="9c5a3-105">Ein Benutzer kann ein Audio-oder Videogerät (beispielsweise ein Headset oder eine Kamera) an den lokalen Computer (beispielsweise einen Thin-Client oder einen neu gezielten Computer) anschließen.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="9c5a3-106">Der Benutzer kann eine Verbindung mit dem virtuellen Computer herstellen, sich beim lync 2013-Client anmelden, der auf dem virtuellen Computer ausgeführt wird, und an Echtzeit-Audio-und Videokommunikation teilnehmen, als ob der Client lokal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="9c5a3-107">Das lync-VDI-Plug-in ist eine eigenständige Anwendung, die auf dem lokalen Computer installiert wird und die Verwendung lokaler Audio-und Videogeräte mit dem auf dem virtuellen Computer ausgeführten lync 2013-Client ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="9c5a3-108">Für das Plug-in ist es nicht erforderlich, dass lync auf dem lokalen Computer installiert wird.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="9c5a3-109">Nachdem sich der Benutzer beim lync 2013-Client angemeldet hat, der auf dem virtuellen Computer ausgeführt wird, fordert lync den Benutzer auf, seine Anmeldeinformationen erneut einzugeben, um eine Verbindung mit dem lync-VDI-Plug-in herzustellen, das auf dem lokalen Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="9c5a3-110">Nachdem diese Verbindung hergestellt wurde, ist der Benutzer bereit, Audio-und Videoanrufe zu tätigen und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="9c5a3-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9c5a3-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9c5a3-111">In This Section</span></span>

  - [<span data-ttu-id="9c5a3-112">Voraussetzungen für das Lync VDI-Plug-In in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c5a3-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="9c5a3-113">Vorbereiten der Lync Server 2013-Umgebung für VDI</span><span class="sxs-lookup"><span data-stu-id="9c5a3-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="9c5a3-114">Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer</span><span class="sxs-lookup"><span data-stu-id="9c5a3-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="9c5a3-115">Problembehandlung beim lync VDI-Plug-in in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c5a3-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="9c5a3-116">Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c5a3-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

