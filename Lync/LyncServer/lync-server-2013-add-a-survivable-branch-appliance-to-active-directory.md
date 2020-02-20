---
title: 'Lync Server 2013: Hinzufügen eines Survivable Branch Appliance zu Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fca31c97e0d059cda9f6b39a0e17e8350a37cf52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="c6da0-102">Hinzufügen eines Survivable Branch Appliance zu Active Directory in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6da0-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6da0-103">_**Letztes Änderungsstand des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="c6da0-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="c6da0-104">Wenn Sie ein Survivable Branch Appliance bereitstellen möchten, müssen Sie den Survivable Branch Appliance Active Directory-Domänendienste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c6da0-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="c6da0-105">Führen Sie dieses Verfahren am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="c6da0-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6da0-106">Führen Sie dieses Verfahren nur aus, wenn Sie ein Survivable Branch Appliance bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6da0-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="c6da0-107">Führen Sie ihn nicht aus, wenn Sie ein Survivable Branch Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c6da0-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="c6da0-108">So fügen Sie den Active Directory-Domänendiensten eine Survivable Branch Appliance hinzu</span><span class="sxs-lookup"><span data-stu-id="c6da0-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="c6da0-109">Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.</span><span class="sxs-lookup"><span data-stu-id="c6da0-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="c6da0-110">Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="c6da0-111">Klicken Sie im Menü **Aktionen** auf **Neu** und dann auf **Computer**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="c6da0-112">Geben Sie im Dialogfeld **Neues Objekt – Computer** einen Namen für das Survivable Branch Appliance Computer Objekt ein (beispielsweise BranchOffice1), und klicken Sie dann auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="c6da0-113">Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die Gruppe "RTCUniversalSBATechnicians" hinzu, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c6da0-114">Ein Mitglied der Gruppe "RTCUniversalSBATechnicians" am Zweigstellenstandort wird dieses Gerät später der Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c6da0-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="c6da0-115">Klicken Sie auf **OK** , um das Survivable Branch Appliance Computerobjekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c6da0-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="c6da0-116">Klicken Sie auf **Start** und auf **Verwaltung** und anschließend auf **ADSI-Editor**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="c6da0-117">Klicken Sie im **ADSI-Editor** mit der rechten Maustaste auf das Computerobjekt, das Sie im vorherigen Schritt erstellt haben, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="c6da0-118">Klicken Sie in der Attributliste auf **servicePrincipalName** und anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="c6da0-119">Geben Sie im Feld **Hinzuzufügender Wert** Host\</SBA\> - \<FQDN ein\> , wobei SBA FQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch Appliance ist.</span><span class="sxs-lookup"><span data-stu-id="c6da0-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="c6da0-120">Geben Sie beispielsweise **HOST/BranchOffice1.contoso.com** ein.</span><span class="sxs-lookup"><span data-stu-id="c6da0-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="c6da0-121">Klicken Sie auf **OK**, um die Attributeinstellung **servicePrincipalName** zu speichern, und klicken Sie dann auf **OK**, um die Eigenschaften des Computerobjekts zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c6da0-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="c6da0-122">Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie auf **Neu** und anschließend auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="c6da0-123">Geben Sie Informationen in den Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch Appliance Techniker zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6da0-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="c6da0-124">Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **Einer Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="c6da0-125">Geben Sie unter **Geben Sie die zu verwendenden Objektnamen ein** den Wert **RTCUniversalSBATechnicians** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6da0-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="c6da0-126">Wiederholen Sie die Schritte 12 bis 15 für jeden Techniker am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="c6da0-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="c6da0-127">**Nächster Schritt**: [Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="c6da0-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

