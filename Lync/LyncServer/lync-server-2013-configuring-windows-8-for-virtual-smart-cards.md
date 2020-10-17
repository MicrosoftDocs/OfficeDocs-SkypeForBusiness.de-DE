---
title: 'Lync Server 2013: Konfigurieren von Windows 8 für virtuelle Smartcards'
description: 'Lync Server 2013: Konfigurieren von Windows 8 für virtuelle Smartcards.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112047f91a20dd552c628fb33eba7bb9ad3d0f01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542161"
---
# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="c9529-103">Konfigurieren Windows 8 für die Verwendung virtueller Smartcards mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9529-103">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9529-104">_**Letztes Änderungsstand des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="c9529-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="c9529-105">Ein Faktor, der bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcard-Technologie berücksichtigt werden muss, sind die Kosten der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="c9529-105">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="c9529-106">Windows 8 bietet eine Reihe von neuen Sicherheitsfunktionen, und eines der interessantesten neuen Features ist die Unterstützung virtueller Smartcards.</span><span class="sxs-lookup"><span data-stu-id="c9529-106">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="c9529-107">Für Computer, die mit einem TPM-Chip (Trusted Platform Module) ausgestattet sind, der die Spezifikationsversion 1,2 erfüllt, können Organisationen jetzt die Vorteile der Smartcard-Anmeldung nutzen, ohne dass zusätzliche Investitionen in Hardware getätigt werden.</span><span class="sxs-lookup"><span data-stu-id="c9529-107">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="c9529-108">Weitere Informationen finden Sie unter Verwenden virtueller Smartcards mit Windows 8 unter [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365) .</span><span class="sxs-lookup"><span data-stu-id="c9529-108">For more information, see Using Virtual Smart Cards with Windows 8 at [https://go.microsoft.com/fwlink/p/?LinkId=313365](https://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="c9529-109">So konfigurieren Sie Windows 8 für virtuelle Smartcards</span><span class="sxs-lookup"><span data-stu-id="c9529-109">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="c9529-110">Melden Sie sich mit den Anmeldeinformationen eines lync-aktivierten Benutzers am Windows 8 Computer an.</span><span class="sxs-lookup"><span data-stu-id="c9529-110">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="c9529-111">Bewegen Sie den Cursor auf der Windows 8 Start Seite in die untere rechte Ecke des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="c9529-111">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="c9529-112">Wählen Sie die **Such** Option aus, und suchen Sie dann nach **Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="c9529-112">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="c9529-113">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie dann **als Administrator ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="c9529-113">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="c9529-114">Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9529-114">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="c9529-115">Überprüfen Sie in der TPM-Verwaltungskonsole, ob Ihre TPM-Spezifikationsversion mindestens 1,2</span><span class="sxs-lookup"><span data-stu-id="c9529-115">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9529-116">Wenn Sie ein Dialogfeld erhalten, das besagt, dass ein kompatibles TPM (Trust Platform Module) nicht gefunden werden kann, stellen Sie sicher, dass der Computer über ein kompatibles TPM-Modul verfügt und im System-BIOS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c9529-116">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="c9529-117">Schließen der TPM-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="c9529-117">Close the TPM management console</span></span>

8.  <span data-ttu-id="c9529-118">Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="c9529-118">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9529-119">Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert angeben möchten, verwenden Sie stattdessen die/PIN-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="c9529-119">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="c9529-120">Öffnen Sie an der Eingabeaufforderung die Computer Verwaltungskonsole, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9529-120">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="c9529-121">Wählen Sie in der Konsole Computer Verwaltung die Option **Geräteverwaltung**aus.</span><span class="sxs-lookup"><span data-stu-id="c9529-121">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="c9529-122">Erweitern Sie **Smart Card Readers**.</span><span class="sxs-lookup"><span data-stu-id="c9529-122">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="c9529-123">Stellen Sie sicher, dass der neue virtuelle Smartcard-Leser erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c9529-123">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

