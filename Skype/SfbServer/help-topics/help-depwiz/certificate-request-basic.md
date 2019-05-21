---
title: Zertifikatsanforderung (Grundlagen)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: Die Seite Name und Sicherheitseinstellungen enthält ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bit-Länge des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen können.
ms.openlocfilehash: 66b9506086207fc8803bae9b77d39ee9f12ac43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302941"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="469fc-103">Zertifikatsanforderung (Grundlagen)</span><span class="sxs-lookup"><span data-stu-id="469fc-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="469fc-104">Die Seite **Name und Sicherheitseinstellungen** enthält ein Textfeld zum Definieren eines **Anzeigenamens**, eine Dropdownliste für die Bit- **Länge** des Paars aus privatem und öffentlichem Schlüssel sowie ein Kontrollkästchen, mit dem Sie **den privaten Schlüssel des Zertifikats als kennzeichnen können. exportierbar**.</span><span class="sxs-lookup"><span data-stu-id="469fc-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="469fc-105">Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.</span><span class="sxs-lookup"><span data-stu-id="469fc-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="469fc-106">Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="469fc-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="469fc-107">Wenn Sie das Kontrollkästchen für **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aktivieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="469fc-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="469fc-108">Dies ist nur erforderlich, wenn Sie einen Pool von Edgeserver für den Media Relay Authentication Service (MRAS) erstellen.</span><span class="sxs-lookup"><span data-stu-id="469fc-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="469fc-109">Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie nur dann den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen auswählen, wenn dies unbedingt erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="469fc-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

