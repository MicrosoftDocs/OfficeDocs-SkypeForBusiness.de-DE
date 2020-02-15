---
title: 'Lync Server 2013: anmelden und Verwenden von lync 2013 auf dem virtuellen Computer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e530f24150bac692717cefb2412712bf3bf8dd1c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="66781-102">Anmelden und Verwenden von lync 2013 auf dem virtuellen Computer</span><span class="sxs-lookup"><span data-stu-id="66781-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66781-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="66781-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="66781-104">Nachdem das VDI-Plug-in aktiviert wurde, werden die folgenden Schritte ausgeführt, wenn sich der Benutzer bei lync 2013 anmeldet.</span><span class="sxs-lookup"><span data-stu-id="66781-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="66781-105">Der Benutzer gibt seine Anmeldeinformationen im lync 2013-Client ein, der auf dem virtuellen Computer läuft.</span><span class="sxs-lookup"><span data-stu-id="66781-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="66781-106">Nachdem lync die Verfügbarkeit des VDI-Plug-ins erkannt hat, fordert lync den Benutzer auf, seine Anmeldeinformationen erneut einzugeben.</span><span class="sxs-lookup"><span data-stu-id="66781-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="66781-107">Es wird empfohlen, in diesem Dialogfeld das Kontrollkästchen **Kennwort speichern** zu aktivieren, damit der Benutzer seine Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="66781-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="66781-108">Lync beginnt mit dem VDI-Plug-in zu koppeln.</span><span class="sxs-lookup"><span data-stu-id="66781-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="66781-109">Bevor die Kopplung abgeschlossen ist, zeigt der Client zwei Symbole in der lync-Statusleiste an.</span><span class="sxs-lookup"><span data-stu-id="66781-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="66781-110">Das Symbol in der linken oberen Ecke gibt an, dass keine Audiogeräte verfügbar sind, und das blinkende Symbol unten rechts zeigt an, dass die VDI-Kopplung in Bearbeitung ist, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="66781-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="66781-111">![Lync-VDI-Symbol mit erfolgreicher Kopplung](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync-VDI-Symbol mit erfolgreicher Kopplung")</span><span class="sxs-lookup"><span data-stu-id="66781-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="66781-112">Nach einer erfolgreichen VDI-Kopplung ändern sich die Symbole und zeigen nun das für Anrufe verwendete Audiogerät bzw. den Erfolg der VDI-Kopplung an:</span><span class="sxs-lookup"><span data-stu-id="66781-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="66781-113">![Lync-VDI-Paarungs Symbol mit Erfolg](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync-VDI-Paarungs Symbol mit Erfolg")</span><span class="sxs-lookup"><span data-stu-id="66781-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="66781-114">Nachdem lync mit dem VDI-Plug-in paarweise zusammengepaßt hat, kann der Benutzer seine Anwesenheit auf lync-kompatiblen Geräten sehen, die mit dem lokalen Computer verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="66781-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="66781-115">Nun kann der Benutzer Anrufe wie gewohnt tätigen oder entgegennehmen.</span><span class="sxs-lookup"><span data-stu-id="66781-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

