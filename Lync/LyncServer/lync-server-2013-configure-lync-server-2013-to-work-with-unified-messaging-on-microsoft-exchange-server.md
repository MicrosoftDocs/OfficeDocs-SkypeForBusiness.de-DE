---
title: 'Lync Server 2013: Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27909f4ae6231b1452cbfefdd82e0a0eb107c6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="75331-102">Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="75331-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="75331-103">_**Letztes Änderungsdatum des Themas:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="75331-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="75331-104">Für diesen Schritt ist das Exchange um-Integrations Dienstprogramm (OcsUmUtil. exe) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75331-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="75331-105">Dieses Tool befindet sich auf dem lync Server 2013-Server in.. \\Programmdateien\\(Common\\files) Microsoft lync\\Server 2013-Support Ordner.</span><span class="sxs-lookup"><span data-stu-id="75331-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="75331-106">Ausführen des Exchange um-Integrationstools</span><span class="sxs-lookup"><span data-stu-id="75331-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="75331-107">Das Exchange um-Integrations Dienstprogramm muss von einem Benutzerkonto mit den folgenden Merkmalen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="75331-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="75331-108">Mitgliedschaft in den Gruppen "RTCUniversalServerAdmins" und "RtcUniversalUserAdmins" (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen).</span><span class="sxs-lookup"><span data-stu-id="75331-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="75331-109">Benutzerrechte innerhalb der Domäne, um Kontaktobjekte im angegebenen Organisationseinheitscontainer (OU) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75331-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="75331-110">Wenn Sie das Exchange um-Integrations Dienstprogramm ausführen, führt es die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="75331-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="75331-111">Erstellt Kontaktobjekte für jede automatische Telefonzentrale und Teilnehmerzugriffsnummer, die von Enterprise-VoIP-Benutzern verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="75331-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="75331-112">Überprüft, ob der Name der einzelnen Enterprise-VoIP-Wählpläne dem zugehörigen Unified Messaging-Wähl Plan Telefonkontext entspricht.</span><span class="sxs-lookup"><span data-stu-id="75331-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="75331-113">Dieser Abgleich ist nur erforderlich, wenn der um-Wählplan unter einer *früheren* Exchange-Version als Exchange 2010 Service Pack 1 (SP1) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="75331-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75331-114">Bevor Sie das Exchange um-Integrations Dienstprogramm ausführen, stellen Sie sicher, dass Sie die folgenden Schritte ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="75331-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="75331-115">Erstellen Sie einen oder mehrere Exchange um-Wählpläne, wie in der Exchange-Produktdokumentation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75331-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="75331-116">Informationen zu Microsoft Exchange Server 2010 finden &quot;Sie unter Erstellen&quot; von um- <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>Wähleinstellungen unter.</span><span class="sxs-lookup"><span data-stu-id="75331-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=186177">http://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="75331-117">Informationen zu Microsoft Exchange Server 2007 Service Pack 1 (SP1) finden &quot;Sie unter Erstellen eines Unified Messaging-SIP-URI&quot; - <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>Wähl Plans unter.</span><span class="sxs-lookup"><span data-stu-id="75331-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="http://go.microsoft.com/fwlink/p/?linkid=185771">http://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="75331-118">Erstellen Sie einen oder mehrere entsprechende lync Server-Wählpläne, wie unter <a href="lync-server-2013-create-a-dial-plan.md">Erstellen eines Wählplans in lync Server 2013</a>beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75331-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="75331-119">Wenn Sie eine Version von Exchange verwenden, die älter als Microsoft Exchange Server 2010 SP1 ist, müssen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des entsprechenden Exchange Unified Messaging (um) SIP-Wählplans im einfachen Namen der lync Server 2013-Wähleinstellungen eingeben. <STRONG> </STRONG>Feld ein.</span><span class="sxs-lookup"><span data-stu-id="75331-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="75331-120">Wenn Sie Microsoft Exchange Server 2010 SP1 oder das neueste Service Pack verwenden, ist diese Wählplannamens Übereinstimmung nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="75331-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="75331-121">Erstellen Sie eine automatische Telefonzentrale, und stellen Sie sicher, dass die Nummer des Teilnehmerzugriffs und die Nummer der automatischen Telefonzentrale im E. 164-Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="75331-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="75331-122">So führen Sie das Exchange um-Integrations Dienstprogramm aus</span><span class="sxs-lookup"><span data-stu-id="75331-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="75331-123">Öffnen Sie auf einem Front-End-Server eine Eingabeaufforderung, und geben Sie **CD% COMMONPROGRAMFILES\\%\\Microsoft lync Server 2013-Unterstützung**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="75331-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="75331-124">Geben Sie **OcsUmUtil. exe**ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="75331-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="75331-125">Klicken Sie auf **Daten laden** , um alle vertrauenswürdigen Exchange-Gesamtstrukturen zu finden.</span><span class="sxs-lookup"><span data-stu-id="75331-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="75331-126">Wählen Sie in der Liste **SIP** -Wählpläne einen um-SIP-Wählplan aus, für den Sie Kontaktobjekte erstellen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="75331-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="75331-127">Übernehmen Sie im Feld **Kontakt** die Standardorganisationseinheit, oder klicken Sie auf **Durchsuchen** , um die **OU-Auswahl**zu starten.</span><span class="sxs-lookup"><span data-stu-id="75331-127">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**.</span></span> <span data-ttu-id="75331-128">Im Feld " **OU-Auswahl** " können Sie eine OU auswählen und auf **OK**klicken, oder Sie können auf **neue Organisations** Einheit erstellen klicken, um eine neue Organisationseinheit unter dem Stamm oder einer anderen ou in der Domäne zu erstellen (beispielsweise "ou = RTC Special Accounts, DC = FourthCoffee, DC = com"). , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75331-128">In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75331-129">Der Distinguished Name (DN) der Organisationseinheit, die Sie ausgewählt oder erstellt haben, wird jetzt im Feld <STRONG>Organisationseinheit</STRONG> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75331-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="75331-130">Übernehmen Sie im Feld **Name** entweder den Standardnamen des Wählplans, oder geben Sie einen neuen Anzeigenamen für das zu erstellende Kontaktobjekt ein.</span><span class="sxs-lookup"><span data-stu-id="75331-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75331-131">Wenn Sie beispielsweise ein Kontaktobjekt für einen Teilnehmerzugriff erstellen, können Sie ihm einfach nur den Abonnenten Zugriff nennen.</span><span class="sxs-lookup"><span data-stu-id="75331-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="75331-132">Übernehmen Sie im Feld **SIP-Adresse** entweder die standardmäßige SIP-Adresse, oder geben Sie eine neue SIP-Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="75331-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75331-133">Wenn Sie eine neue SIP-Adresse eingeben, muss Sie mit <STRONG>SIP:</STRONG> (also "SIP:" einschließlich des Doppelpunkts) beginnen.</span><span class="sxs-lookup"><span data-stu-id="75331-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="75331-134">Wählen Sie in der Liste **Server oder Pool** den Standard Edition-Server oder den Front-End-Pool aus, in dem das Kontaktobjekt aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="75331-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75331-135">Vorzugsweise ist der ausgewählte Pool derselbe Pool, in dem Benutzer, die für Enterprise-VoIP aktiviert sind, und Exchange um bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="75331-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="75331-136">Wählen Sie in der Liste **Telefonnummer** entweder **Rufnummer eingeben** oder **diese Pilotnummer in Exchange um verwenden aus** , und geben Sie dann eine Telefonnummer ein.</span><span class="sxs-lookup"><span data-stu-id="75331-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="75331-137">Wählen Sie \*\*\*\* in der Liste Kontakttyp den Typ des Kontakts aus, den Sie erstellen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75331-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="75331-138">Wiederholen Sie die Schritte 1 bis 10 für weitere Kontaktobjekte, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="75331-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75331-139">Sie sollten für jede automatische Telefonzentrale mindestens einen Kontakt erstellen.</span><span class="sxs-lookup"><span data-stu-id="75331-139">You should create at least one contact for each auto attendant.</span></span> <span data-ttu-id="75331-140">Wenn Sie den externen Zugriff wünschen, benötigen Sie außerdem einen Kontakt für den Teilnehmerzugriff und geben direkte Durchwahlnummern (DID) an.</span><span class="sxs-lookup"><span data-stu-id="75331-140">If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="75331-141">Um zu überprüfen, ob die Kontaktobjekte erstellt wurden, öffnen Sie Active Directory-Benutzer und-Computer, und wählen Sie die Organisationseinheit aus, in der die Objekte erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="75331-141">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created.</span></span> <span data-ttu-id="75331-142">Die Kontaktobjekte sollten im Detailbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75331-142">The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="75331-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="75331-143"></span></span></div>

