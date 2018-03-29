---
title: Bereitstellen von Clients für Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="a7776-103">Bereitstellen von Clients für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7776-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7776-104">**Zusammenfassung:** Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a7776-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="a7776-105">Wie Sie Skype für Unternehmen für die Benutzer bereitstellen, hängt gibt an, ob Sie Skype für Unternehmen im Rahmen eines Plans für Office 365 erworben haben, oder Sie eine Volume lizenzierte Version von Skype für Unternehmen erworben.</span><span class="sxs-lookup"><span data-stu-id="a7776-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="a7776-106">**Office 365** Wenn Sie einen Office 365-Plan haben, der Skype für Unternehmen enthält, wird die Installation-Technologie, die verwendet wird, Klick-und-Los aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a7776-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="a7776-107">Mit Office 365 können Sie Ihre Benutzer Skype für Unternehmen für sich selbst über Office 365-Portal installieren lassen.</span><span class="sxs-lookup"><span data-stu-id="a7776-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="a7776-108">Oder Sie können Skype für Unternehmen Herunterladen der Software in Ihr lokales Netzwerk und dann mit der vorhandenen Software von Tools wie Microsoft System Center Configuration Manager für die Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a7776-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="a7776-109">Installationsinformationen zu Skype für Unternehmen, die mit Office 365 enthalten ist, finden Sie unter [Bereitstellen der Skype für Business-Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="a7776-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="a7776-110">**Volume lizenziert** Wenn Sie eine Volumenlizenz-Version von Skype für Unternehmen verfügen, ist die Installation-Technologie, die verwendet wird, wird Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="a7776-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="a7776-111">Ein Windows Installer-basierten Installationspaket umfasst mehrere MSI-Dateien.</span><span class="sxs-lookup"><span data-stu-id="a7776-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="a7776-112">Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert.</span><span class="sxs-lookup"><span data-stu-id="a7776-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="a7776-113">Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="a7776-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="a7776-114">In den Themen in diesem Abschnitt wird beschrieben, wie verwenden und Anpassen von Windows Installer, um die Skype für Business-Client, die Benutzern in Ihrer normalen Verfahren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a7776-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7776-115">Meeting-Add-in für Skype für Unternehmen, welche meeting Verwaltung von Besprechungen Outlook unterstützt Client für messaging und Zusammenarbeit, wird automatisch mit Skype für Unternehmen Online.</span><span class="sxs-lookup"><span data-stu-id="a7776-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a7776-116">Das Setupprogramm für Office 365 wird nicht mit frühere Versionen von Lync oder Office Communicator deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a7776-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="a7776-117">Die Skype für Business-Client installiert Side-by-Side mit anderen Lync oder Office Communicator-Clients.</span><span class="sxs-lookup"><span data-stu-id="a7776-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="a7776-118">Installieren von Windows-clients</span><span class="sxs-lookup"><span data-stu-id="a7776-118">Installing Windows clients</span></span>

- [<span data-ttu-id="a7776-119">Anpassen von Windows-Client-Installation in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7776-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="a7776-120">Konfigurieren der Clientumgebung mit Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a7776-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="a7776-121">Konfigurieren von Smart Kontaktliste in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a7776-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="a7776-122">Installieren von Gerät-clients</span><span class="sxs-lookup"><span data-stu-id="a7776-122">Installing device clients</span></span>

- [<span data-ttu-id="a7776-123">Installieren und Testen von Skype für Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a7776-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="a7776-124">Installieren und Testen von Skype für Unternehmen für iOS</span><span class="sxs-lookup"><span data-stu-id="a7776-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="a7776-125">Bereitstellen von Skype Raum System in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a7776-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="a7776-126">Bereitstellen von Skype Raum Systemen v2</span><span class="sxs-lookup"><span data-stu-id="a7776-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="a7776-127">Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7776-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="a7776-128">Bereitstellen von herunterladbaren Webclients in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a7776-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="a7776-129">Anpassen der Mac-Clientumgebung in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="a7776-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="a7776-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7776-130">See also</span></span>

#### 

[<span data-ttu-id="a7776-131">Bereitstellen der Skype für Business-Client für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a7776-131">Deploy the Skype for Business client for your organization</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

