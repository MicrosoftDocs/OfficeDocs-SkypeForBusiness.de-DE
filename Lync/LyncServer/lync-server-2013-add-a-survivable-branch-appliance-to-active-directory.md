---
title: 'Lync Server 2013: Hinzufügen eines Survivable Branch Appliance zu Active Directory'
description: 'Lync Server 2013: Fügen Sie Active Directory eine Survivable Branch Appliance hinzu.'
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
ms.openlocfilehash: bd06332679be0819cf3002f344a62a7ce1d5a9f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567891"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="aff7c-103">Hinzufügen eines Survivable Branch Appliance zu Active Directory in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aff7c-103">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff7c-104">_**Letztes Änderungsstand des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="aff7c-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="aff7c-105">Wenn Sie ein Survivable Branch Appliance bereitstellen möchten, müssen Sie den Survivable Branch Appliance Active Directory-Domänendienste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aff7c-105">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="aff7c-106">Führen Sie dieses Verfahren am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="aff7c-106">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="aff7c-107">Führen Sie dieses Verfahren nur aus, wenn Sie ein Survivable Branch Appliance bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="aff7c-107">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="aff7c-108">Führen Sie ihn nicht aus, wenn Sie ein Survivable Branch Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="aff7c-108">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="aff7c-109">So fügen Sie den Active Directory-Domänendiensten eine Survivable Branch Appliance hinzu</span><span class="sxs-lookup"><span data-stu-id="aff7c-109">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="aff7c-110">Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.</span><span class="sxs-lookup"><span data-stu-id="aff7c-110">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="aff7c-111">Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-111">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="aff7c-112">Klicken Sie im Menü **Aktionen** auf **Neu** und dann auf **Computer**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-112">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="aff7c-113">Geben Sie im Dialogfeld **Neues Objekt – Computer** einen Namen für das Survivable Branch Appliance Computer Objekt ein (beispielsweise BranchOffice1), und klicken Sie dann auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-113">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="aff7c-114">Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die Gruppe "RTCUniversalSBATechnicians" hinzu, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-114">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aff7c-115">Ein Mitglied der Gruppe "RTCUniversalSBATechnicians" am Zweigstellenstandort wird dieses Gerät später der Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aff7c-115">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="aff7c-116">Klicken Sie auf **OK** , um das Survivable Branch Appliance Computerobjekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="aff7c-116">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="aff7c-117">Klicken Sie auf **Start** und auf **Verwaltung** und anschließend auf **ADSI-Editor**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-117">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="aff7c-118">Klicken Sie im **ADSI-Editor** mit der rechten Maustaste auf das Computerobjekt, das Sie im vorherigen Schritt erstellt haben, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-118">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="aff7c-119">Klicken Sie in der Attributliste auf **servicePrincipalName** und anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-119">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="aff7c-120">Geben Sie im Feld **Hinzuzufügender Wert** \<SBA FQDN\> \<SBA FQDN\> den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch Appliance ein.</span><span class="sxs-lookup"><span data-stu-id="aff7c-120">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="aff7c-121">Geben Sie beispielsweise **HOST/BranchOffice1.contoso.com** ein.</span><span class="sxs-lookup"><span data-stu-id="aff7c-121">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="aff7c-122">Klicken Sie auf **OK**, um die Attributeinstellung **servicePrincipalName** zu speichern, und klicken Sie dann auf **OK**, um die Eigenschaften des Computerobjekts zu speichern.</span><span class="sxs-lookup"><span data-stu-id="aff7c-122">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="aff7c-123">Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie auf **Neu** und anschließend auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-123">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="aff7c-124">Geben Sie Informationen in den Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch Appliance Techniker zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aff7c-124">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="aff7c-125">Klicken Sie in **Active Directory-Benutzer und -Computer** mit der rechten Maustaste auf **Users**, klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **Einer Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-125">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="aff7c-126">Geben Sie unter **Geben Sie die zu verwendenden Objektnamen ein** den Wert **RTCUniversalSBATechnicians** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aff7c-126">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="aff7c-127">Wiederholen Sie die Schritte 12 bis 15 für jeden Techniker am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="aff7c-127">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="aff7c-128">**Nächster Schritt**: [Hinzufügen von Zweigstellenstandorten zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="aff7c-128">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

