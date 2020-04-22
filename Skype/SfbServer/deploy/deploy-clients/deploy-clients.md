---
title: Bereitstellen von Clients für Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über die Installationsmethoden von Enterprise-Clients für Skype for Business.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778281"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="328fd-103">Bereitstellen von Clients für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="328fd-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="328fd-104">**Zusammenfassung:** Übersicht über die Installationsmethoden von Enterprise-Clients für Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="328fd-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="328fd-105">Wie Sie Skype for Business für Ihre Benutzer bereitstellen, hängt davon ab, ob Sie Skype for Business im Rahmen eines Office 365 Plans erworben haben oder eine Volumenlizenzversion von Skype for Business erworben haben.</span><span class="sxs-lookup"><span data-stu-id="328fd-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="328fd-106">**Office 365** Wenn Sie über einen Office 365 Plan verfügen, der Skype for Business enthält, wird die verwendete Installationstechnologie als Klick-und-Los bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="328fd-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="328fd-107">Mit Office 365 können Sie den Benutzern die Installation von Skype for Business über das Microsoft 365 Admin Center ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="328fd-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="328fd-108">Oder Sie können Skype for Business für Ihre Benutzer bereitstellen, indem Sie die Software in Ihr lokales Netzwerk herunterladen und dann Ihre vorhandenen Softwarebereitstellungstools verwenden, beispielsweise mit dem Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="328fd-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="328fd-109">Installationsinformationen zu Skype for Business, die mit Office 365 geliefert werden, finden Sie unter [deploy the Skype for Business Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="328fd-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="328fd-110">**Volumen lizenziert** Wenn Sie über eine Volumenlizenzversion des Skype for Business 2015-oder 2016-Clients verfügen, wird die verwendete Installationstechnologie als Windows Installer (MSI) verwendet.</span><span class="sxs-lookup"><span data-stu-id="328fd-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="328fd-111">Ein Windows Installer-basiertes Installationspaket besteht aus mehreren MSI-Dateien.</span><span class="sxs-lookup"><span data-stu-id="328fd-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="328fd-112">Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert.</span><span class="sxs-lookup"><span data-stu-id="328fd-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="328fd-113">Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="328fd-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="328fd-114">Der Skype for Business 2019-Client verwendet Klick-und-Los-Installationsprogramme.</span><span class="sxs-lookup"><span data-stu-id="328fd-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="328fd-115">In den Themen in diesem Abschnitt wird beschrieben, wie Sie den Windows Installer verwenden und anpassen, um den Skype for Business-Client über die normalen Verfahren für Ihre Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="328fd-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="328fd-116">Das Skype-Besprechungs-Add-in für Microsoft Office, das die Besprechungsverwaltung über den Outlook-Client für Messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype for Business-Clients installiert.</span><span class="sxs-lookup"><span data-stu-id="328fd-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="328fd-117">Mit dem Setupprogramm für Office 365 werden frühere Versionen von lync nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="328fd-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="328fd-118">Der Skype for Business Client wird nebeneinander mit anderen lync-Clients installiert.</span><span class="sxs-lookup"><span data-stu-id="328fd-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="328fd-119">Installieren von Windows-Clients</span><span class="sxs-lookup"><span data-stu-id="328fd-119">Installing Windows clients</span></span>

- [<span data-ttu-id="328fd-120">Anpassen der Windows-Clientinstallation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="328fd-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="328fd-121">Konfigurieren der Clientumgebung mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="328fd-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="328fd-122">Konfigurieren der intelligenten Kontaktliste in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="328fd-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="328fd-123">Installieren von Geräteclients</span><span class="sxs-lookup"><span data-stu-id="328fd-123">Installing device clients</span></span>

- [<span data-ttu-id="328fd-124">Installieren und Testen von Skype for Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="328fd-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="328fd-125">Installieren und Testen von Skype for Business für IOS</span><span class="sxs-lookup"><span data-stu-id="328fd-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="328fd-126">Bereitstellen des lync VDI-Plug-ins mit Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="328fd-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="328fd-127">Bereitstellen von Webdownload-Clients in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="328fd-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="328fd-128">Anpassen der Mac-Clientumgebung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="328fd-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="328fd-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="328fd-129">See also</span></span>

[<span data-ttu-id="328fd-130">Bereitstellen des Skype for Business-Clients in Office 365</span><span class="sxs-lookup"><span data-stu-id="328fd-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
