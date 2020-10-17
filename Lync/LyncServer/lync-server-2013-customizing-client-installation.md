---
title: 'Lync Server 2013: Anpassen der Clientinstallation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755a53b6afc089093f5efbfd2a90699e12e66b8f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516692"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="e3884-102">Anpassen der Clientinstallation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3884-102">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3884-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e3884-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e3884-104">Unternehmensadministratoren können die Office 2013 Installation von Windows Installer-basierten (MSI)-Installationen mithilfe der in diesem Abschnitt erläuterten Methoden anpassen.</span><span class="sxs-lookup"><span data-stu-id="e3884-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="e3884-105">Da kein einzelnes Tool alle Anpassungsoptionen bereitstellt, verwenden Sie wahrscheinlich eine Kombination dieser Methoden in ihrer lync 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e3884-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="e3884-106">Dabei kann es sich mindestens um die in den folgenden Abschnitten beschriebenen Tools handeln:</span><span class="sxs-lookup"><span data-stu-id="e3884-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="e3884-107">[Verwenden des Office-Anpassungstools (OAT) in lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) zum Anpassen von Setupoptionen und Features für lync und andere Office-Programme.</span><span class="sxs-lookup"><span data-stu-id="e3884-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="e3884-108">[Verwenden von Config.xml zum Ausführen von Installationsaufgaben in lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) , um den Pfad des Netzwerkinstallationspfads anzugeben und eine unbeaufsichtigte Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e3884-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="e3884-109">[Verwenden von Setup-Befehlszeilenoptionen in lync Server 2013](lync-server-2013-using-setup-command-line-options.md) , um die Config.xml Datei anzugeben, die während der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3884-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="e3884-110">[Konfigurieren von clientbootstrapping-Richtlinien in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) mithilfe des MMC-Snap-Ins Gruppenrichtlinienobjekt-Editor.</span><span class="sxs-lookup"><span data-stu-id="e3884-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="e3884-p102">Bei der Bereitstellung der Office-Produktsuite passen Sie wahrscheinlich noch weitere Optionen für Ihre Bereitstellung an. Die Themen in diesem Abschnitt bieten Ihnen einen Überblick über die Anpassungstools und gehen auf spezifische Aspekte von Lync ein. Außerdem finden Sie dort Links zu detaillierter Office-Hilfe für die einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="e3884-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

