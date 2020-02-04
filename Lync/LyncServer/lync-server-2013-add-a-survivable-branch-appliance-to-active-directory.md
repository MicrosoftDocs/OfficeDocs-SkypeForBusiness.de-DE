---
title: 'Lync Server 2013: Hinzufügen einer Survivable Branch Appliance zu Active Directory'
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="ddae1-102">Hinzufügen einer Survivable Branch Appliance zu Active Directory in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddae1-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddae1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="ddae1-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="ddae1-104">Wenn Sie beabsichtigen, eine Survivable Branch-Appliance bereitzustellen, müssen Sie die Survivable Branch-Appliance zu Active Directory-Domänendiensten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ddae1-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="ddae1-105">Führen Sie dieses Verfahren am zentralen Standort aus.</span><span class="sxs-lookup"><span data-stu-id="ddae1-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ddae1-106">Führen Sie dieses Verfahren nur aus, wenn Sie eine Survivable Branch-Appliance bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ddae1-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="ddae1-107">Führen Sie das Programm nicht aus, wenn Sie einen Überlebenden Verzweigungs Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ddae1-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="ddae1-108">So fügen Sie eine Survivable Branch-Appliance zu Active Directory-Domänendiensten hinzu</span><span class="sxs-lookup"><span data-stu-id="ddae1-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="ddae1-109">Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Unternehmensadministratoren" an.</span><span class="sxs-lookup"><span data-stu-id="ddae1-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="ddae1-110">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="ddae1-111">Klicken Sie im Menü **Aktionen** auf **neu** , und klicken Sie dann auf **Computer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="ddae1-112">Geben Sie im Dialogfeld **Neues Objekt – Computer** einen Namen für das Survivable Branch Appliance-Computer Objekt ein (beispielsweise BranchOffice1), und klicken Sie dann auf **ändern**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="ddae1-113">Fügen Sie im Dialogfeld **Benutzer oder Gruppe auswählen** die RTCUniversalSBATechnicians-Gruppe hinzu, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ddae1-114">Ein Mitglied der RTCUniversalSBATechnicians-Gruppe auf der Zweigstelle fügt dieses Gerät später zur Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="ddae1-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="ddae1-115">Klicken Sie auf **OK** , um das Survivable Branch Appliance-Computerobjekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ddae1-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="ddae1-116">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **ADSI-Bearbeitung**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="ddae1-117">Klicken Sie in der **ADSI-Bearbeitung**mit der rechten Maustaste auf das Computerobjekt, das Sie in den vorherigen Schritten erstellt haben, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="ddae1-118">Klicken Sie in der Liste Attribut auf **servicePrincipalName**, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="ddae1-119">Geben Sie im Feld **Wert zum Hinzufügen** den Namen\<Host/\> SBA \<-FQDN\> ein, wobei SBA-FQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) Ihrer Survivable Branch Appliance ist.</span><span class="sxs-lookup"><span data-stu-id="ddae1-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="ddae1-120">Geben Sie beispielsweise **Host/BranchOffice1. contoso. com**ein.</span><span class="sxs-lookup"><span data-stu-id="ddae1-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="ddae1-121">Klicken Sie auf **OK** , um die **servicePrincipalName** -Attributeinstellung zu speichern, und klicken Sie dann auf **OK** , um die Computerobjekt Eigenschaften zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ddae1-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="ddae1-122">Klicken Sie in **Active Directory-Benutzer und-Computer**mit der rechten Maustaste auf **Benutzer**, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="ddae1-123">Geben Sie Informationen in den Assistenten ein, um ein Domänenbenutzerkonto für einen Survivable Branch Appliance-Techniker zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddae1-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="ddae1-124">Klicken Sie in **Active Directory-Benutzer und-Computer**auf **Benutzer**, klicken Sie mit der rechten Maustaste auf das Benutzerobjekt, und klicken Sie dann auf **zu einer Gruppe hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="ddae1-125">Geben Sie in **Geben Sie die zu wählenden Objektnamen ein** **RTCUniversalSBATechnicians**ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddae1-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="ddae1-126">Wiederholen Sie die Schritte 12-15 für jeden Zweigstellen Techniker.</span><span class="sxs-lookup"><span data-stu-id="ddae1-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="ddae1-127">**Nächster Schritt**: [Hinzufügen von Zweigstellen zu Ihrer Topologie in lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="ddae1-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

