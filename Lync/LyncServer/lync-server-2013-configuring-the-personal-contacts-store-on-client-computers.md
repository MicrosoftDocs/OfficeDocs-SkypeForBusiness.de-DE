---
title: 'Lync Server 2013: Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6020182c0083ecadcb65c07fa71be213f9458f0f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532342"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a><span data-ttu-id="2e30f-102">Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e30f-102">Configuring the personal contacts store on client computers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e30f-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="2e30f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="2e30f-104">Wenn Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren, wird empfohlen, den persönlichen Kontaktspeicher auf allen Clientcomputern zu konfigurieren, auf denen Microsoft lync 2010 läuft.</span><span class="sxs-lookup"><span data-stu-id="2e30f-104">If you are integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 then it is recommended that you configure the personal contact store on any client computers running Microsoft Lync 2010.</span></span> <span data-ttu-id="2e30f-105">Insbesondere sollten Sie lync so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass Benutzer diese Entscheidung nicht außer Kraft setzen können.</span><span class="sxs-lookup"><span data-stu-id="2e30f-105">In particular, you should configure Lync to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="2e30f-106">Dies kann durch Erstellen und Konfigurieren eines Registrierungswerts auf jedem Clientcomputer erfolgen.</span><span class="sxs-lookup"><span data-stu-id="2e30f-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>

<span data-ttu-id="2e30f-107">Beachten Sie, dass dies auf Computern mit lync 2013 nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2e30f-107">Note that this is not required on computers running Lync 2013.</span></span>

<span data-ttu-id="2e30f-108">Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2e30f-108">To configure this value on a single computer, complete the following procedure:</span></span>

1.  <span data-ttu-id="2e30f-109">Klicken Sie auf dem Clientcomputer auf **Start** , und klicken Sie dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="2e30f-109">On the client computer, click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="2e30f-110">Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="2e30f-110">In the **Run** dialog box, type regedit and then press ENTER.</span></span>

3.  <span data-ttu-id="2e30f-111">Erweitern Sie im Registrierungs- **Editor \_ den Knoten HKEY lokaler \_ Computer**, erweitern Sie **Software**, **Richtlinien**und dann **Microsoft**, und erweitern Sie dann **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="2e30f-111">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>

4.  <span data-ttu-id="2e30f-112">Klicken Sie mit der rechten Maustaste auf **Communicator**, dann auf **neu**, und klicken Sie dann auf **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="2e30f-112">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>

5.  <span data-ttu-id="2e30f-113">Nachdem der neue Wert erstellt wurde, geben Sie **PersonalContactStoreOverride** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="2e30f-113">After the new value is created, type **PersonalContactStoreOverride** and then press ENTER to rename the value.</span></span>

6.  <span data-ttu-id="2e30f-114">Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.</span><span class="sxs-lookup"><span data-stu-id="2e30f-114">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="2e30f-115">Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e30f-115">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="2e30f-116">Ausführliche Informationen finden Sie in der Dokumentation zur Gruppenrichtlinie unter [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) .</span><span class="sxs-lookup"><span data-stu-id="2e30f-116">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

