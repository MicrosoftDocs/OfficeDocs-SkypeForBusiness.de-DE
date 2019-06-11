---
title: 'Lync Server 2013: Testen des Standard Edition-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="b2442-102">Testen des Standard Edition-Servers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2442-102">Test the Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2442-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b2442-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b2442-104">Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellungeines Standard Edition-Servers testen.</span><span class="sxs-lookup"><span data-stu-id="b2442-104">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="b2442-105">So testen Sie die Bereitstellungeines Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="b2442-105">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="b2442-106">Verwenden Sie Active Directory-Computer und-Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf der lync Server Control Panel installiert ist) zur **CSAdministrator** -Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2442-106">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="b2442-107">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="b2442-107">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2442-108">Das Benutzerkonto kann nicht der lokale Administrator des Servers sein, auf dem lync Server 2013, Standard Edition, ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b2442-108">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="b2442-109">Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, erhalten Sie eine Fehlermeldung, wenn Sie die lync Server 2013-Systemsteuerung öffnen, in der angegeben ist, dass "nicht autorisiert: der Zugriff verweigert wird aufgrund eines Autorisierungs Fehlers bei der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC)".</span><span class="sxs-lookup"><span data-stu-id="b2442-109">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="b2442-110">Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die lync Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="b2442-110">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="b2442-111">Starten Sie die lync Server-Systemsteuerung, und geben Sie bei Aufforderung Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="b2442-111">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="b2442-112">Die lync Server 2013-Systemsteuerung zeigt Bereitstellungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b2442-112">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="b2442-113">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass es sich bei dem Dienststatus um ein Computersymbol mit einem grünen Pfeil und ein grünes Häkchen neben jeder lync Server-Serverrolle handelt, die bereitgestellt und online geschaltet wurde.</span><span class="sxs-lookup"><span data-stu-id="b2442-113">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="b2442-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und aktivieren Sie dann die beiden Benutzer für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b2442-114">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="b2442-115">Melden Sie einen Benutzer an einem Computer, der mit der Domäne verbunden ist, und dem anderen Benutzer auf einem anderen Computer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="b2442-115">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="b2442-116">Installieren Sie lync Server 2013 auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden können und Sofortnachrichten senden können.</span><span class="sxs-lookup"><span data-stu-id="b2442-116">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2442-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2442-117">See Also</span></span>


[<span data-ttu-id="b2442-118">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2442-118">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

