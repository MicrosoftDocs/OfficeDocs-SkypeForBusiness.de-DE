---
title: 'Lync Server 2013: Testen der Standard Edition-Server'
description: 'Lync Server 2013: Testen Sie die Standard Edition-Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35dc13fc01979cc8b293d0647a7886b7d65d7669
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576010"
---
# <a name="test-the-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="2ab9e-103">Testen der Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ab9e-103">Test the Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ab9e-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2ab9e-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2ab9e-105">Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellungeines Standard Edition-Server testen.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-105">The following procedure describes how to test the deployment of a Standard Edition server.</span></span>

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a><span data-ttu-id="2ab9e-106">So testen Sie die Bereitstellung eines Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="2ab9e-106">To test the deployment of a Standard Edition Server</span></span>

1.  <span data-ttu-id="2ab9e-107">Verwenden Sie Active Directory Computer und Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf dem lync Server-Systemsteuerung installiert ist) zur Gruppe **CSAdministrator** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-107">Use Active Directory Computers and Users to add the Active Directory user object of the administrator role for the Lync Server 2013 deployment (on which Lync Server Control Panel is installed) to the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="2ab9e-108">Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-108">If the user object is currently logged on, log off and then log on again to register the new group assignment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ab9e-109">Das Benutzerkonto kann nicht der lokale Administrator des Servers sein, auf dem lync Server 2013 Standard Edition installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-109">The user account cannot be the local administrator of the server running Lync Server 2013, Standard Edition.</span></span> <span data-ttu-id="2ab9e-110">Wenn Sie der Gruppe CsAdministors die entsprechenden Benutzer und Gruppen nicht hinzufügen, wird beim Öffnen lync Server 2013 Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff aufgrund eines RBAC-Autorisierungs Fehlers (Role-Based Access Control) verweigert wird."</span><span class="sxs-lookup"><span data-stu-id="2ab9e-110">If you do not add the appropriate users and groups to the CsAdministors group, you will receive an error when opening Lync Server 2013 Control Panel, which states that “Unauthorized: Access is denied due to a role-based access control (RBAC) authorization failure.”</span></span>

    
    </div>

3.  <span data-ttu-id="2ab9e-111">Melden Sie sich mit dem Administratorkonto bei dem Computer an, auf dem lync Server-Systemsteuerung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-111">Use the administrative account to log on to the computer where Lync Server Control Panel is installed.</span></span>

4.  <span data-ttu-id="2ab9e-112">Wenn Sie dazu aufgefordert werden, starten Sie lync Server-Systemsteuerung und geben Sie Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-112">Start Lync Server Control Panel and provide credentials, if prompted.</span></span> <span data-ttu-id="2ab9e-113">In lync Server 2013 Systemsteuerung werden Bereitstellungsinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-113">Lync Server 2013 Control Panel displays deployment information.</span></span>

5.  <span data-ttu-id="2ab9e-114">Klicken Sie in der linken Navigationsleiste auf **Topologie**, und vergewissern Sie sich, dass der Dienststatus ein Computersymbol mit einem grünen Pfeil ist und neben jeder lync Server Server Rolle, die bereitgestellt und online geschaltet wurde, ein grünes Häkchen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-114">In the left navigation bar, click **Topology**, and then confirm that the service status is a computer icon with a green arrow and there is a green check mark next to each Lync Server server role that has been deployed and brought online.</span></span>

6.  <span data-ttu-id="2ab9e-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und aktivieren Sie dann die beiden Benutzer für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-115">In the left navigation bar, click **Users**, and then enable the two users for Lync Server 2013.</span></span>

7.  <span data-ttu-id="2ab9e-116">Melden Sie einen Benutzer bei einem Computer, der Teil der Domäne ist, und den anderen Benutzer bei einem anderen Computer in der Domäne an.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-116">Log one user on to a computer that is joined to the domain, and the other user on to another computer in the domain.</span></span>

8.  <span data-ttu-id="2ab9e-117">Installieren Sie lync Server 2013 auf den beiden Clientcomputern, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden und Sofortnachrichten miteinander senden können.</span><span class="sxs-lookup"><span data-stu-id="2ab9e-117">Install Lync Server 2013 on each of the two client computers, and then verify that both users can sign in to Lync Server 2013 and can send instant messages to each other.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ab9e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ab9e-118">See Also</span></span>


[<span data-ttu-id="2ab9e-119">Bereitstellen von Clients und Geräten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ab9e-119">Deploying clients and devices in Lync Server 2013</span></span>](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

