---
title: Anpassen von Windows-Client-Installation in Skype für Business Server
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Zusammenfassung: Übersicht über Installationsmethoden und Tools für Skype für Unternehmen.'
ms.openlocfilehash: d6458c1ec81ea67162a53107582249f301102ebd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890613"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="040d4-103">Anpassen von Windows-Client-Installation in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="040d4-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="040d4-104">**Zusammenfassung:** Übersicht über Installationsmethoden und Tools für Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="040d4-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="040d4-105">Installationsinformationen zu Skype für Unternehmen, die mit Office 365 enthalten ist, finden Sie unter [Bereitstellen der Skype für Business-Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="040d4-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="040d4-106">Unternehmensadministratoren können die Windows Installer-basierten (MSI) Installation von Volumenlizenzversionen von Skype für Business anpassen, mithilfe der Methods in diesem Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="040d4-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="040d4-107">Da keine einzelnes Tool alle Optionen zur Anpassung bereitstellt, wahrscheinlich verwenden eine Kombination der folgenden Methoden in Ihrer Skype für die Business-Bereitstellung Sie.</span><span class="sxs-lookup"><span data-stu-id="040d4-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="040d4-108">Sie können die in den folgenden Abschnitten beschriebenen Tools verwenden:</span><span class="sxs-lookup"><span data-stu-id="040d4-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="040d4-109">[Verwendung der Office-Anpassungstool (OAT) in Skype für Business Server](use-the-office-customization-tool-oct.md) zum Anpassen von Setupoptionen und Funktionen für Skype für Unternehmen und anderen Office-Programmen.</span><span class="sxs-lookup"><span data-stu-id="040d4-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="040d4-110">[Verwenden von "config.xml" zum Ausführen von Installationsaufgaben in Skype für Business Server](use-config-xml-to-perform-installation-tasks.md) Geben Sie den Pfad des Netzwerkinstallationspfads und unbeaufsichtigte Installation durchführen.</span><span class="sxs-lookup"><span data-stu-id="040d4-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="040d4-111">[Verwenden Sie Setup-Befehlszeilenoptionen in Skype für Business Server](use-setup-command-line-options.md) zum Angeben der Datei Config.xml, die während der Installation verwendet.</span><span class="sxs-lookup"><span data-stu-id="040d4-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="040d4-112">[Configure Client bootstrapping Policies in Skype für Business Server](configure-client-bootstrapping-policies.md) mithilfe des Gruppenrichtlinienobjekt-Editor-MMC-Snap-in.</span><span class="sxs-lookup"><span data-stu-id="040d4-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="040d4-113">Möglicherweise werden weitere Optionen, den, die Sie konfigurieren, wie Sie die Office-Suite Produkte bereitstellen möchten, benötigen.</span><span class="sxs-lookup"><span data-stu-id="040d4-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="040d4-114">In den Themen in diesem Abschnitt geben Sie eine Übersicht über diese Anpassungstools und werden Aspekte bestimmte zu Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="040d4-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="040d4-115">Außerdem finden Sie dort Links zu detaillierter Office-Hilfe für die einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="040d4-115">Included are links to detailed Office help for each tool.</span></span> 
  

