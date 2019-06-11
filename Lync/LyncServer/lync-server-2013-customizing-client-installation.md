---
title: 'Lync Server 2013: Anpassen der Clientinstallation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd099f5d57174eb02733abd70bb99a91679a1328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="310ae-102">Anpassen der Clientinstallation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="310ae-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="310ae-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="310ae-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="310ae-104">Unternehmensadministratoren können die Windows Installer-basierte Installation (MSI) von Office 2013 mithilfe der in diesem Abschnitt beschriebenen Methoden anpassen.</span><span class="sxs-lookup"><span data-stu-id="310ae-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="310ae-105">Da kein einzelnes Tool alle Anpassungsoptionen bereitstellt, verwenden Sie wahrscheinlich eine Kombination dieser Methoden in ihrer lync 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="310ae-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="310ae-106">Sie können die in den folgenden Abschnitten beschriebenen Tools mindestens verwenden:</span><span class="sxs-lookup"><span data-stu-id="310ae-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="310ae-107">[Verwenden Sie das Office-Anpassungs Tool (OAT) in lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) , um die Setupoptionen und Features für lync und andere Office-Programme anzupassen.</span><span class="sxs-lookup"><span data-stu-id="310ae-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="310ae-108">[Verwenden von "config. xml" zum Ausführen von Installationsaufgaben in lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) , um den Pfad des Netzwerkinstallationspunkts anzugeben und eine unbeaufsichtigte Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="310ae-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="310ae-109">[Verwenden Sie die Setup-Befehlszeilenoptionen in lync Server 2013](lync-server-2013-using-setup-command-line-options.md) , um die Datei config. XML anzugeben, die während der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="310ae-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="310ae-110">[Konfigurieren von Client-Trap Ping-Richtlinien in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mithilfe des MMC-Snap-Ins "Gruppenrichtlinienobjekt-Editor".</span><span class="sxs-lookup"><span data-stu-id="310ae-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="310ae-111">Bei der Bereitstellung der Office-Produktsuite passen Sie wahrscheinlich noch weitere Optionen für Ihre Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="310ae-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="310ae-112">Die Themen in diesem Abschnitt enthalten eine Übersicht über diese Anpassungstools und erläutern lync-spezifische Aspekte.</span><span class="sxs-lookup"><span data-stu-id="310ae-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="310ae-113">Außerdem finden Sie dort Links zu detaillierter Office-Hilfe für die einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="310ae-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

