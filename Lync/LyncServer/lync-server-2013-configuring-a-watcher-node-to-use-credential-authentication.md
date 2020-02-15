---
title: 'Lync Server 2013: Konfigurieren eines Watcher-Knotens zur Verwendung der Anmeldeinformationen-Authentifizierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38a06c7ea40bd30f962484c8ce0d882c9633bf0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a><span data-ttu-id="526a5-102">Konfigurieren eines Watcher-Knotens für die Verwendung der Anmeldeinformationen-Authentifizierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="526a5-102">Configuring a watcher node to use credential authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="526a5-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="526a5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="526a5-p101">Wenn Ihr Monitorknotencomputer außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie ein etwas anderes Verfahren anwenden, um diesen Monitorknoten für die Ausführung synthetischer Transaktionen zu konfigurieren. Beachten Sie, dass Sie keinen Pool mit vertrauenswürdigen Anwendungen und keine vertrauenswürdige Anwendung erstellen sollten und ein Zertifikat installieren müssen, über das der Monitorknoten Benachrichtigungen an einen Computer im Umkreisnetzwerk senden kann. Dies bedeutet, dass Sie zwei separate Schritte ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="526a5-p101">If your watcher node computer lies outside the perimeter network, then you must follow a slightly different procedure in order to configure that watcher node to run synthetic transactions. Specifically, you should not create a trusted application pool and a trusted application, and you must install a certificate that enables the watcher node to send alerts to a computer inside the perimeter network. This means that you will need to complete two separate tasks:</span></span>

  - <span data-ttu-id="526a5-107">Aktualisieren der Mitgliedschaft für die Gruppe "RTC Local Read-only Administrators Group" des Computers</span><span class="sxs-lookup"><span data-stu-id="526a5-107">Update the membership in the computer's RTC Local Read-only Administrators Group</span></span>

  - <span data-ttu-id="526a5-108">Installieren der Konfigurationsdateien des Monitorknotens</span><span class="sxs-lookup"><span data-stu-id="526a5-108">Install the watcher node configuration files</span></span>

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a><span data-ttu-id="526a5-109">Aktualisieren der Mitgliedschaft in der Gruppe "RTC Local Read-only Administrators"</span><span class="sxs-lookup"><span data-stu-id="526a5-109">Updating Membership in the RTC Local Read-Only Administrators Group</span></span>

<span data-ttu-id="526a5-p102">Wenn der Monitorknoten außerhalb des Umkreisnetzwerks angeordnet ist, müssen Sie das Netzwerkdienstkonto auf dem Computer mit dem Monitorknoten der Gruppe "RTC Local Read-only Administrators" hinzufügen. Führen Sie dazu für den Monitorknoten die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="526a5-p102">If your watcher node lies outside the perimeter network, you must add the Network Service account to the RTC Local Read-only Administrators group on the watcher node computer. To do this, complete the following procedure on the watcher node:</span></span>

1.  <span data-ttu-id="526a5-112">Klicken Sie auf **Start**, klicken Sie mit der rechten Maustaste auf **Arbeitsplatz**, und klicken Sie dann auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="526a5-112">Click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="526a5-113">Erweitern Sie im Server-Manager die Optionen **Konfiguration** und **Lokale Benutzer und Gruppen**, und klicken Sie dann auf **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="526a5-113">In Server Manager, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>

3.  <span data-ttu-id="526a5-114">Doppelklicken Sie im Bereich "Gruppen" mit der rechten Maustaste auf **RTC Local Read-only Administrators**.</span><span class="sxs-lookup"><span data-stu-id="526a5-114">In the Groups pane, double-click **RTC Local Read-only Administrators**.</span></span>

4.  <span data-ttu-id="526a5-115">Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="526a5-115">In the **RTC Local Read-only Administrators Properties** dialog box, click **Add**.</span></span>

5.  <span data-ttu-id="526a5-116">Klicken Sie im Dialogfeld für die Auswahl von Benutzern, Computern, Dienstkonten oder Gruppen\*\*\*\* auf **Standorte**.</span><span class="sxs-lookup"><span data-stu-id="526a5-116">In the **Select Users, Computers, Service Accounts, or Groups** dialog box, click **Locations**.</span></span>

6.  <span data-ttu-id="526a5-117">Wählen Sie im Dialogfeld **Standorte** den Namen des Monitorknotencomputers aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="526a5-117">In the **Locations** dialog box, select the name of the watcher node computer, and then click **OK**.</span></span>

7.  <span data-ttu-id="526a5-118">Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** den Text **Netzwerkdienst** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="526a5-118">In the **Enter object names to select** box, type **Network Service**, and then click **OK**.</span></span>

8.  <span data-ttu-id="526a5-119">Klicken Sie im Dialogfeld mit den Eigenschaften von **RTC Local Read-only Administrators** auf **OK**, und schließen Sie den **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="526a5-119">In the **RTC Local Read-only Administrators Properties** dialog box, click **OK**, and then close **Server Manager**.</span></span>

<span data-ttu-id="526a5-120">Starten Sie den Monitorknotencomputer neu.</span><span class="sxs-lookup"><span data-stu-id="526a5-120">Restart the watcher node computer.</span></span>

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a><span data-ttu-id="526a5-121">Installieren der Konfigurationsdateien des Monitorknotens</span><span class="sxs-lookup"><span data-stu-id="526a5-121">Installing the Watcher Node Configuration Files</span></span>

<span data-ttu-id="526a5-122">Nachdem der Monitorknotencomputer neu gestartet wurde, ist der nächste Schritt das Ausführen der Datei "Watchernode.msi".</span><span class="sxs-lookup"><span data-stu-id="526a5-122">After the watcher node computer has restarted, your next step is to run the file Watchernode.msi.</span></span> <span data-ttu-id="526a5-123">Um diese Datei auszuführen, öffnen Sie die lync Server 2013 Verwaltungsshell, indem Sie auf **Start**und **Alle Programme**klicken, auf **lync Server 2013**und dann auf **lync Server-Verwaltungsshell**klicken.</span><span class="sxs-lookup"><span data-stu-id="526a5-123">To run this file, open the Lync Server 2013 Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server 2013**, and then clicking **Lync Server Management Shell**.</span></span> <span data-ttu-id="526a5-124">Geben Sie im lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE (stellen Sie sicher, dass Sie den tatsächlichen Pfad zu Ihrer Kopie von Watchernode. msi angeben):</span><span class="sxs-lookup"><span data-stu-id="526a5-124">In the Lync Server Management Shell, type the following command and then press ENTER (be sure and specify the actual path to your copy of Watchernode.msi):</span></span>

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> <span data-ttu-id="526a5-p104">Wie bereits erwähnt, kann die Datei "Watchernode.msi" auch über ein Befehlsfenster mit Eingabeaufforderung ausgeführt werden. Klicken Sie zum Öffnen eines Befehlsfensters auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie dann auf <STRONG>Als Administrator ausführen</STRONG>. Geben Sie den bereits gezeigten Befehl ein, nachdem das Befehlsfenster geöffnet wurde.</span><span class="sxs-lookup"><span data-stu-id="526a5-p104">As noted previously, Watchernode.msi can also be run from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same command as shown earlier.</span></span>



</div>

<span data-ttu-id="526a5-128">Der Aushandlungsmodus wird verwendet, wenn der Monitorknoten nicht als Pool mit vertrauenswürdigen Anwendungen eingerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="526a5-128">The Negotiate mode is used any time the watcher node cannot be set up as a trusted application pool.</span></span> <span data-ttu-id="526a5-129">In diesem Modus müssen Administratoren Testbenutzerkennwörter für den Monitorknoten verwalten.</span><span class="sxs-lookup"><span data-stu-id="526a5-129">In this mode, administrators will need to manage test user passwords on the watcher node.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

