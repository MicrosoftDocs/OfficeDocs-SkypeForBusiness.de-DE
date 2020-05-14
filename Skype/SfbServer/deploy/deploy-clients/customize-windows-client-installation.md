---
title: Anpassen der Windows-Clientinstallation in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Zusammenfassung: Übersicht über Installationsmethoden und Tools für Skype for Business.'
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220835"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="a6516-103">Anpassen der Windows-Clientinstallation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a6516-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="a6516-104">**Zusammenfassung:** Übersicht über Installationsmethoden und Tools für Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a6516-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6516-105">Installationsinformationen zu Skype for Business, die mit Microsoft 365 und Office 365 geliefert werden, finden Sie unter [deploy the Skype for Business Client in Microsoft 365 oder Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="a6516-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="a6516-106">Unternehmensadministratoren können die Windows Installer-basierte (MSI)-Installation von Volumen lizenzierten Versionen von Skype for Business mithilfe der in diesem Abschnitt erläuterten Methoden anpassen.</span><span class="sxs-lookup"><span data-stu-id="a6516-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="a6516-107">Da kein einzelnes Tool alle Anpassungsoptionen bereitstellt, verwenden Sie wahrscheinlich eine Kombination dieser Methoden in Ihrer Skype for Business-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a6516-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="a6516-108">Sie können die in den folgenden Abschnitten beschriebenen Tools verwenden:</span><span class="sxs-lookup"><span data-stu-id="a6516-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="a6516-109">[Verwenden Sie das Office-Anpassungs Tool (OAT) in Skype for Business Server](use-the-office-customization-tool-oct.md) , um Setupoptionen und Features für Skype for Business und andere Office-Programme anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a6516-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="a6516-110">[Verwenden Sie config. XML zum Ausführen von Installationsaufgaben in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) , um den Pfad des Netzwerkinstallationspfads anzugeben und eine unbeaufsichtigte Installation durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a6516-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="a6516-111">[Verwenden Sie Setup-Befehlszeilenoptionen in Skype for Business Server](use-setup-command-line-options.md) , um die Datei "config. xml" anzugeben, die während der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6516-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="a6516-112">[Konfigurieren Sie die clientbootstrapping-Richtlinien in Skype for Business Server](configure-client-bootstrapping-policies.md) mithilfe des MMC-Snap-Ins Gruppenrichtlinienobjekt-Editor.</span><span class="sxs-lookup"><span data-stu-id="a6516-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="a6516-113">Es gibt wahrscheinlich andere Optionen, die Sie bei der Bereitstellung der Office-Produktsuite konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a6516-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="a6516-114">Die Themen in diesem Abschnitt geben einen Überblick über diese Anpassungstools und besprechen die Skype for Business spezifischen Überlegungen.</span><span class="sxs-lookup"><span data-stu-id="a6516-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="a6516-115">Außerdem finden Sie dort Links zu detaillierter Office-Hilfe für die einzelnen Tools.</span><span class="sxs-lookup"><span data-stu-id="a6516-115">Included are links to detailed Office help for each tool.</span></span> 
  

