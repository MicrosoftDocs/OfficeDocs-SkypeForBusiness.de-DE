---
title: 'Lync Server 2013: Aktualisieren von der Evaluierungsversion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 787aa9f1983dc755f1ce9b35ff66320be1d5dba5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="0597b-102">Aktualisieren von der Evaluierungsversion von lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0597b-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0597b-103">_**Letztes Änderungsstand des Themas:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="0597b-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="0597b-104">Wenn Sie die Evaluierungsversion von Microsoft lync Server 2013 installiert haben, müssen Sie diese Installation schließlich mit einer lizenzierten Kopie der Software aktualisieren. Das liegt daran, dass die Evaluierungsversion 180 Tage nach der Installation abläuft.</span><span class="sxs-lookup"><span data-stu-id="0597b-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="0597b-105">Es ist jedoch nicht notwendig, die Evaluierungsversion vollständig zu deinstallieren und anschließend die lizenzierte Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0597b-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="0597b-106">Nachdem Sie einen gültigen Lizenzierungsschlüssel erhalten haben, können Sie stattdessen die Evaluierungsversion von lync Server 2013 aktualisieren, indem Sie auf jedem Computer, der als lync Server Front-End-Server, Director oder Edgeserver fungiert, das folgende Verfahren ausführen.</span><span class="sxs-lookup"><span data-stu-id="0597b-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="0597b-107">Beachten Sie, dass Computer, die für andere Serverrollen (z. B. Monitoring-Server oder Archivierungsserver) verwendet werden, nicht aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0597b-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="0597b-108">Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0597b-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="0597b-109">So aktualisieren Sie einen Computer von der Evaluierungsversion von lync Server 2013 auf die lizenzierte Version der Software:</span><span class="sxs-lookup"><span data-stu-id="0597b-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="0597b-110">**Aktualisieren von der Evaluierungs Version von Microsoft lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="0597b-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="0597b-111">Melden Sie sich beim Computer als lokaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="0597b-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="0597b-112">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0597b-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0597b-113">Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="0597b-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="0597b-114">Möglicherweise müssen Sie den vollständigen Pfad zur Datei SERVER.MSI angeben.</span><span class="sxs-lookup"><span data-stu-id="0597b-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="0597b-115">Diese Datei befindet sich im Installationsordner der lync Server Volume Media-Installationsdateien.</span><span class="sxs-lookup"><span data-stu-id="0597b-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="0597b-116">Nach der Ausführung von Setup geben Sie an einer Eingabeaufforderung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="0597b-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="0597b-117">Wiederholen Sie dieses Verfahren für alle anderen Front-End-Server, Director oder Edgeserver, die eine Evaluierungskopie von lync Server ausführen.</span><span class="sxs-lookup"><span data-stu-id="0597b-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="0597b-118">Dieses Verfahren sollte auch auf allen Zweigstellenservern ausgeführt werden, die mithilfe der lync Server Medien Installationsdateien bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0597b-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="0597b-119">Wenn Sie nicht sicher sind, ob die Evaluierungsversion von lync Server auf einem bestimmten Computer läuft, können Sie dies überprüfen, indem Sie den folgenden Befehl in der lync Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="0597b-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="0597b-120">Das Cmdlet [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) analysiert den lokalen Computer und gibt eine der folgenden Informationen zurück:</span><span class="sxs-lookup"><span data-stu-id="0597b-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="0597b-121">, Dass der lync Server Volumenlizenzschlüssel auf dem Computer installiert wurde, was bedeutet, dass keine Aktualisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0597b-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="0597b-122">, Dass der lync Server Evaluierungslizenz Schlüssel installiert wurde, was bedeutet, dass der Computer aktualisiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="0597b-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="0597b-p104">Auf dem Computer ist kein Volumenlizenzschlüssel erforderlich. Die Aktualisierung der Evaluierungsversion auf die lizenzierte Version ist nur auf Front-End-Servern, Directors und Edgeservern notwendig.</span><span class="sxs-lookup"><span data-stu-id="0597b-p104">That no volume license key is required on the computer. Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

