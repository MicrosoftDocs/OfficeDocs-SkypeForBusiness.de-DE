---
title: Bereitstellen von Clients für Skype für Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Zusammenfassung: Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.'
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985687"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="ffec3-103">Bereitstellen von Clients für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="ffec3-104">**Zusammenfassung:** Übersicht über Enterprise-Client-Installationsmethoden für Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="ffec3-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="ffec3-105">Wie Sie Skype für Unternehmen für die Benutzer bereitstellen, hängt gibt an, ob Sie Skype für Unternehmen im Rahmen eines Plans für Office 365 erworben haben, oder Sie eine Volume lizenzierte Version von Skype für Unternehmen erworben.</span><span class="sxs-lookup"><span data-stu-id="ffec3-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="ffec3-106">**Office 365** Wenn Sie einen Office 365-Plan haben, der Skype für Unternehmen enthält, wird die Installation-Technologie, die verwendet wird, Klick-und-Los aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ffec3-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="ffec3-107">Mit Office 365 können Sie Ihre Benutzer Skype für Unternehmen für sich selbst über Office 365-Portal installieren lassen.</span><span class="sxs-lookup"><span data-stu-id="ffec3-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="ffec3-108">Oder Sie können Skype für Unternehmen Herunterladen der Software in Ihr lokales Netzwerk und dann mit der vorhandenen Software von Tools wie Microsoft System Center Configuration Manager für die Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ffec3-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="ffec3-109">Installationsinformationen zu Skype für Unternehmen, die mit Office 365 enthalten ist, finden Sie unter [Bereitstellen der Skype für Business-Client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="ffec3-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="ffec3-110">**Volume lizenziert** Wenn Sie eine Volume lizenzierte Version von der Skype für Business 2015 oder 2016 Client verfügen, ist die Installation-Technologie, die verwendet wird Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="ffec3-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="ffec3-111">Ein Windows Installer-basierten Installationspaket umfasst mehrere MSI-Dateien.</span><span class="sxs-lookup"><span data-stu-id="ffec3-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="ffec3-112">Ein MSI-Paket mit sprachneutralem Kern wird mit einem oder mehreren sprachenspezifischen Paketen zu einem vollständigen Produkt kombiniert.</span><span class="sxs-lookup"><span data-stu-id="ffec3-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="ffec3-113">Setup fügt die einzelnen Pakete zusammen und führt während und nach der Installation von Office auf den Computern der Benutzer Anpassungs- und Wartungsaufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="ffec3-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="ffec3-114">Die Skype für Business 2019 Client verwendet Klick-und-Los-Installer.</span><span class="sxs-lookup"><span data-stu-id="ffec3-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="ffec3-115">In den Themen in diesem Abschnitt wird beschrieben, wie verwenden und Anpassen von Windows Installer, um die Skype für Business-Client, die Benutzern in Ihrer normalen Verfahren bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ffec3-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ffec3-116">Die Skype-Meeting-Add-in für Microsoft Office, das die besprechungsverwaltung aus dem Outlook-Client für messaging und Zusammenarbeit unterstützt, wird automatisch mit Skype für Business-Clients.</span><span class="sxs-lookup"><span data-stu-id="ffec3-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ffec3-117">Das Setupprogramm für Office 365 wird nicht mit frühere Versionen von Lync deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="ffec3-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="ffec3-118">Die Skype für Business-Client installiert Side-by-Side mit anderen Lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="ffec3-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="ffec3-119">Installieren von Windows-clients</span><span class="sxs-lookup"><span data-stu-id="ffec3-119">Installing Windows clients</span></span>

- [<span data-ttu-id="ffec3-120">Anpassen von Windows-Client-Installation in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="ffec3-121">Konfigurieren der Clientumgebung mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ffec3-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="ffec3-122">Konfigurieren der intelligenten Kontaktliste in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="ffec3-123">Installieren von Gerät-clients</span><span class="sxs-lookup"><span data-stu-id="ffec3-123">Installing device clients</span></span>

- [<span data-ttu-id="ffec3-124">Skype for Business Server 2015: Installieren und Testen von Skype for Business für Windows Phone</span><span class="sxs-lookup"><span data-stu-id="ffec3-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="ffec3-125">Installieren und Testen von Skype for Business für iOS</span><span class="sxs-lookup"><span data-stu-id="ffec3-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="ffec3-126">Bereitstellen von Skype Room System in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="ffec3-127">Bereitstellen von Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="ffec3-127">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="ffec3-128">Bereitstellen des Lync VDI-Plug-in mit Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="ffec3-129">Bereitstellen Sie herunterladbare Webclients in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ffec3-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="ffec3-130">Anpassen der Mac-Clienterfahrung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ffec3-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="ffec3-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffec3-131">See also</span></span>

[<span data-ttu-id="ffec3-132">Bereitstellen der Skype für Business-Client in Office 365</span><span class="sxs-lookup"><span data-stu-id="ffec3-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)