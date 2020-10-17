---
title: 'Lync Server 2013: Erstellen einer neuen PIN-Richtlinie'
description: 'Lync Server 2013: Erstellen einer neuen PIN-Richtlinie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new PIN policy
ms:assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182547(v=OCS.15)
ms:contentKeyID: 48184777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c69a91148ce90829b8bde6d88b1f98ca12ca4683
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554681"
---
# <a name="create-a-new-pin-policy-in-lync-server-2013"></a><span data-ttu-id="ff15e-103">Erstellen einer neuen PIN-Richtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff15e-103">Create a new PIN policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff15e-104">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="ff15e-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="ff15e-105">Sie können die Seite **PIN-Richtlinie** verwenden, um Benutzern, die eine Verbindung zu lync 2013 mit IP-Telefonen herstellen, die PIN-Authentifizierung (Personal Identification Number) zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Lync 2013 with IP Phones.</span></span> <span data-ttu-id="ff15e-106">Stellen Sie zur Verwendung der PIN-Authentifizierung sicher, dass in den Webdiensteinstellungen die Option **PIN-Authentifizierung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ff15e-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span> <span data-ttu-id="ff15e-107">Ausführliche Informationen finden Sie unter [Ändern vorhandener Webdienst-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ff15e-107">For details, see [Modify existing Web Service configuration settings in Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).</span></span>

<span data-ttu-id="ff15e-108">Führen Sie die folgenden Schritte aus, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-108">Follow these steps to create a user-level or a site-level PIN policy.</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="ff15e-109">So erstellen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene</span><span class="sxs-lookup"><span data-stu-id="ff15e-109">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="ff15e-110">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ff15e-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ff15e-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ff15e-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ff15e-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ff15e-113">Klicken Sie in der linken Navigationsleiste auf **Sicherheit** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="ff15e-113">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="ff15e-114">Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="ff15e-114">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ff15e-p103">Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="ff15e-p104">Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="ff15e-120">Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="ff15e-120">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="ff15e-p105">Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein, oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="ff15e-p106">Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="ff15e-126">Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-126">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="ff15e-p107">Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="ff15e-130">Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-130">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="ff15e-p108">Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="ff15e-p109">Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff15e-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ff15e-136">Es wird empfohlen, die Verwendung gängiger Muster nicht zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="ff15e-136">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="ff15e-137">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ff15e-137">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

