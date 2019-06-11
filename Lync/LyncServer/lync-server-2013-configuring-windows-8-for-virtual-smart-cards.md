---
title: 'Lync Server 2013: Konfigurieren von Windows 8 für virtuelle Smartcards'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Windows 8 for Virtual Smart Cards
ms:assetid: 4916c167-4ee3-4f3e-b65c-33e588595112
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308564(v=OCS.15)
ms:contentKeyID: 54973684
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177e5f9786b103c086630984be849c320801a82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-windows-8-for-using-virtual-smart-cards-with-lync-server-2013"></a><span data-ttu-id="5244e-102">Konfigurieren von Windows 8 für die Verwendung virtueller Smartcards mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5244e-102">Configuring Windows 8 for using Virtual Smart Cards with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5244e-103">_**Letztes Änderungsdatum des Themas:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="5244e-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="5244e-104">Ein zu berücksichtigender Faktor bei der Bereitstellung der zweistufigen Authentifizierung und der Smartcardtechnologie sind die Kosten der Implementierung.</span><span class="sxs-lookup"><span data-stu-id="5244e-104">One factor to consider when deploying two-factor authentication and smart card technology is the cost of implementation.</span></span> <span data-ttu-id="5244e-105">Windows 8 bietet eine Reihe neuer Sicherheitsfunktionen, und eines der interessantesten neuen Features ist die Unterstützung virtueller Smartcards.</span><span class="sxs-lookup"><span data-stu-id="5244e-105">Windows 8 provides a number of new security capabilities, and one of the most interesting new features is support for virtual smart cards.</span></span>

<span data-ttu-id="5244e-106">Bei Computern, die mit einem TPM-Chip (Trusted Platform Module) ausgerüstet sind, der die Spezifikationen von Version 1.2 erfüllt, können Organisationen nun die Vorteile einer Smartcardanmeldung nutzen, ohne in zusätzliche Hardware investieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="5244e-106">For computers equipped with a Trusted Platform Module (TPM) chip that meets specification version 1.2, organizations can now get the benefits of smart card logon without making any additional investments in hardware.</span></span> <span data-ttu-id="5244e-107">Weitere Informationen finden Sie unter Verwenden virtueller Smartcards mit Windows 8 unter [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span><span class="sxs-lookup"><span data-stu-id="5244e-107">For more information, see Using Virtual Smart Cards with Windows 8 at [http://go.microsoft.com/fwlink/p/?LinkId=313365](http://go.microsoft.com/fwlink/p/?linkid=313365).</span></span>

<div>

## <a name="to-configure-windows-8-for-virtual-smart-cards"></a><span data-ttu-id="5244e-108">So konfigurieren Sie Windows 8 für virtuelle Smartcards</span><span class="sxs-lookup"><span data-stu-id="5244e-108">To Configure Windows 8 for Virtual Smart Cards</span></span>

1.  <span data-ttu-id="5244e-109">Melden Sie sich mit den Anmeldeinformationen eines lync-fähigen Benutzers beim Windows 8-Computer an.</span><span class="sxs-lookup"><span data-stu-id="5244e-109">Log in to the Windows 8 computer using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="5244e-110">Bewegen Sie den Cursor auf der Windows 8-Startseite in die untere rechte Ecke des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="5244e-110">At the Windows 8 Start screen, move your cursor to the bottom right corner of the screen.</span></span>

3.  <span data-ttu-id="5244e-111">Wählen Sie die Option **Suchen** und suchen Sie dann nach der **Command Prompt**.</span><span class="sxs-lookup"><span data-stu-id="5244e-111">Select the **Search** option, and then search for **Command Prompt**.</span></span>

4.  <span data-ttu-id="5244e-112">Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung** und wählen Sie dann **Als Administrator ausführen** aus.</span><span class="sxs-lookup"><span data-stu-id="5244e-112">Right click on **Command Prompt**, and then select **Run as Administrator**.</span></span>

5.  <span data-ttu-id="5244e-113">Öffnen Sie die TPM-Verwaltungskonsole (Trusted Platform Module), indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="5244e-113">Open the Trusted Platform Module (TPM) Management console by running the following command:</span></span>
    
        Tpm.msc

6.  <span data-ttu-id="5244e-114">Vergewissern Sie sich in der TPM-Verwaltungskonsole, dass die TPM-Spezifikationsversion mindestens 1.2 ist.</span><span class="sxs-lookup"><span data-stu-id="5244e-114">From the TPM management console, verify that your TPM specification version is at least 1.2</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5244e-115">Wird ein Dialogfeld angezeigt, in dem gemeldet wird, dass kein kompatibles Trusted Platform Module (TPM) gefunden wurde, sollten Sie sich vergewissern, dass der Computer ein kompatibles TPM hat und dass dieses im System-BIOS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5244e-115">If you receive a dialog stating that a Compatible Trust Platform Module (TPM) cannot be found, verify that the computer has a compatible TPM module and that it is enabled in the system BIOS.</span></span>

    
    </div>

7.  <span data-ttu-id="5244e-116">Schließen Sie die TPM-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="5244e-116">Close the TPM management console</span></span>

8.  <span data-ttu-id="5244e-117">Erstellen Sie über die Eingabeaufforderung eine neue virtuelle Smartcard, indem Sie folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="5244e-117">From the command prompt, create a new virtual smart card using the following command:</span></span>
    
        TpmVscMgr create /name MyVSC /pin default /adminkey random /generate
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5244e-118">Wenn Sie beim Erstellen der virtuellen Smartcard einen benutzerdefinierten PIN-Wert bereitstellen möchten, verwenden Sie „/pin prompt“ anstelle von „/pin default“.</span><span class="sxs-lookup"><span data-stu-id="5244e-118">To provide a custom PIN value when creating the virtual smart card, use /pin prompt instead.</span></span>

    
    </div>

9.  <span data-ttu-id="5244e-119">Öffnen Sie über die Eingabeaufforderung die Computerverwaltungskonsole, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="5244e-119">From the command prompt, open the Computer Management console by running the following command:</span></span>
    
        CompMgmt.msc

10. <span data-ttu-id="5244e-120">Wählen Sie in der Computerverwaltungskonsole den Eintrag **Geräte-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="5244e-120">In the Computer Management console, select **Device Management**.</span></span>

11. <span data-ttu-id="5244e-121">Erweitern Sie **Smartcard-Leser**.</span><span class="sxs-lookup"><span data-stu-id="5244e-121">Expand **Smart card readers**.</span></span>

12. <span data-ttu-id="5244e-122">Vergewissern Sie sich, dass der neue virtuelle Smartcardleser erfolgreich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5244e-122">Verify that the new virtual smart card reader has been created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

