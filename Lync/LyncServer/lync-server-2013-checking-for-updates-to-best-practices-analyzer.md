---
title: 'Lync Server 2013: Überprüfen auf Updates für Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Checking for updates to Best Practices Analyzer
ms:assetid: 06f1da8b-99a7-4871-911e-bfb7542baced
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204645(v=OCS.15)
ms:contentKeyID: 48183307
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a52aec0748bb5e96de0b3e6dafae4e05ddf9c15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-for-updates-to-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="1c9ce-102">Überprüfen auf Updates für Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c9ce-102">Checking for updates to Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c9ce-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1c9ce-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1c9ce-104">Wenn Sie Best Practices Analyzer starten, bietet Ihnen das Tool eine Option zum Suchen nach den neuesten Updates für das Tool.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-104">When you start Best Practices Analyzer, the tool provides you with an option to search for the latest updates to the tool.</span></span> <span data-ttu-id="1c9ce-105">Wenn ein Update verfügbar ist, können Sie das Update herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-105">If an update is available, you can download the update.</span></span> <span data-ttu-id="1c9ce-106">Wenn Sie keine Updates herunterladen möchten oder wenn Best Practices Analyzer nicht auf das Internet zugreifen kann, können Sie weiterhin die Version verwenden, die sich bereits auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-106">If you choose not to download updates, or if Best Practices Analyzer cannot access the Internet, you can continue to use the version that is already on the computer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1c9ce-107">Wenn Sie die Proxyauthentifizierung für den Zugriff auf das Internet benötigen, kann Best Practices Analyzer nicht auf neue Updates zugreifen, die Sie herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-107">If you need proxy authentication to access the Internet, Best Practices Analyzer cannot access new updates for you to download.</span></span> <span data-ttu-id="1c9ce-108">Sie können die aktuelle Version von RtcBPA. msi jedoch manuell aus dem Microsoft Download Center unter <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>herunterladen.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-108">However, you can manually download the latest version of RtcBPA.msi from the Microsoft Download Center at <A href="http://go.microsoft.com/fwlink/p/?linkid=266539">http://go.microsoft.com/fwlink/p/?linkId=266539</A>.</span></span> <span data-ttu-id="1c9ce-109">Nachdem Sie die Datei heruntergeladen haben, können Sie Sie auf den Computer kopieren, auf dem Sie Best Practices Analyzer aktualisieren möchten, und mithilfe der MSI-Datei die neue Version des Tools auf diesem Computer installieren.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-109">After downloading the file, you can copy it to the computer on which you want to update Best Practices Analyzer and use the .msi file to install the new version of the tool on that computer.</span></span>



</div>

<span data-ttu-id="1c9ce-110">Um Best Practices Analyzer-Regeln zu aktualisieren, müssen Sie das Tool als Administrator auf dem lokalen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-110">To update Best Practices Analyzer rules, you must run the tool as an Administrator on the local computer.</span></span> <span data-ttu-id="1c9ce-111">Wenn Sie nicht mit einem Konto angemeldet sind, das Mitglied der Gruppe Administratoren ist, und Updates erkannt werden, schließen Sie Best Practices Analyzer, und führen Sie dann das folgende Verfahren aus, um das Programm zu starten.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-111">If you are not logged on using an account that is a member of the Administrators group and updates are detected, close Best Practices Analyzer, and then use the following procedure to start the program.</span></span>

<div>

## <a name="to-open-best-practices-analyzer-as-administrator-to-check-for-updates"></a><span data-ttu-id="1c9ce-112">So öffnen Sie Best Practices Analyzer als Administrator, um nach Updates zu suchen</span><span class="sxs-lookup"><span data-stu-id="1c9ce-112">To open Best Practices Analyzer as Administrator to check for updates</span></span>

1.  <span data-ttu-id="1c9ce-113">Klicken Sie auf einem Computer, auf dem Best Practices Analyzer installiert ist, auf **Start**, zeigen Sie auf **Microsoft lync Server 2013**, klicken Sie mit der rechten Maustaste auf **Best Practices Analyzer**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-113">On a computer on which Best Practices Analyzer is installed, click **Start**, point to **Microsoft Lync Server 2013**, right-click **Best Practices Analyzer**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1c9ce-114">Geben Sie die Anmeldeinformationen eines Kontos an, das ein Mitglied der Gruppe "Administratoren" ist.</span><span class="sxs-lookup"><span data-stu-id="1c9ce-114">Specify credentials of an account that is a member of the Administrators group.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

