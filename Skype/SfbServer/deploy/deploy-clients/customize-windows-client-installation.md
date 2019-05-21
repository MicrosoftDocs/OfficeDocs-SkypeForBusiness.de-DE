---
title: Anpassen der Windows-Clientinstallation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Zusammenfassung: Übersicht über Installationsmethoden und Tools für Skype for Business.'
ms.openlocfilehash: 40e5b9145f06038e76aee0b77b287e6dce9a8b3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288578"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="599bc-103">Anpassen der Windows-Clientinstallation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="599bc-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="599bc-104">**Zusammenfassung:** Übersicht über Installationsmethoden und Tools für Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="599bc-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="599bc-105">Installationsinformationen zu Skype for Business, die in Office 365 enthalten sind, finden Sie unter [Bereitstellen des Skype for Business-Clients in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="599bc-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="599bc-106">Unternehmensadministratoren können die Windows Installer-basierte (MSI)-Installation von Volumen lizenzierten Versionen von Skype for Business mithilfe der in diesem Abschnitt beschriebenen Methoden anpassen.</span><span class="sxs-lookup"><span data-stu-id="599bc-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="599bc-107">Da kein einzelnes Tool alle Anpassungsoptionen bereitstellt, verwenden Sie wahrscheinlich eine Kombination dieser Methoden in Ihrer Skype for Business-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="599bc-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="599bc-108">Sie können die in den folgenden Abschnitten beschriebenen Tools verwenden:</span><span class="sxs-lookup"><span data-stu-id="599bc-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="599bc-109">[Verwenden Sie das Office-Anpassungs Tool (OAT) in Skype for Business Server](use-the-office-customization-tool-oct.md) , um die Setupoptionen und Funktionen für Skype for Business und andere Office-Programme anzupassen.</span><span class="sxs-lookup"><span data-stu-id="599bc-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="599bc-110">[Verwenden Sie "config. xml", um Installationsaufgaben in Skype for Business Server durchzuführen](use-config-xml-to-perform-installation-tasks.md) , um den Pfad des Netzwerkinstallationspunkts anzugeben und eine unbeaufsichtigte Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="599bc-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="599bc-111">[Verwenden Sie die Setup-Befehlszeilenoptionen in Skype for Business Server](use-setup-command-line-options.md) , um die Datei config. XML anzugeben, die während der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="599bc-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="599bc-112">[Konfigurieren Sie die Richtlinien für Client-Bootstrapping in Skype for Business Server](configure-client-bootstrapping-policies.md) mithilfe des MMC-Snap-Ins Gruppenrichtlinienobjekt-Editor.</span><span class="sxs-lookup"><span data-stu-id="599bc-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="599bc-113">Es gibt wahrscheinlich andere Optionen, die Sie konfigurieren möchten, wenn Sie die Office-Produktsuite bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="599bc-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="599bc-114">Die Themen in diesem Abschnitt geben einen Überblick über diese Anpassungstools und besprechen Überlegungen, die speziell für Skype for Business gelten.</span><span class="sxs-lookup"><span data-stu-id="599bc-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="599bc-115">Außerdem finden Sie dort Links zu detaillierter Office-Hilfe für die einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="599bc-115">Included are links to detailed Office help for each tool.</span></span> 
  

