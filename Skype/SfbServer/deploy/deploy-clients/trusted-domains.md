---
title: Skype Room System – Vertrauenswürdige Domänen
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
ms.openlocfilehash: eacc468508ba9107534ce4ac729edf0d0d6c895d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287870"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="b1de2-103">Skype Room System – Vertrauenswürdige Domänen</span><span class="sxs-lookup"><span data-stu-id="b1de2-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="b1de2-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b1de2-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="b1de2-105">Vertrauenswürdige Domänen</span><span class="sxs-lookup"><span data-stu-id="b1de2-105">Trusted domains</span></span>

<span data-ttu-id="b1de2-106">Der Skype for Business-Client zeigt ein Dialogfeld an, in dem Benutzer das Zertifikat über den Skype for Business-Server akzeptieren können, wenn sich die SIP-Domäne des Benutzerkontos von dem Namen unterscheidet, der in dem Betreff oder dem Betreff-Alternativnamen des Zertifikats angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b1de2-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="b1de2-107">Wenn das für Skype for Business Server in Ihrer Organisation konfigurierte Zertifikat nicht über den SIP-Domänennamen des Skype Room-System Kontos in Betreff oder Betreff alt ist, müssen Sie die auf dem Zertifikat angezeigten Domänen unter den vertrauenswürdigen Domänen konfigurieren. Registrierungsschlüssel auf dem Skype Room System Console-Computer.</span><span class="sxs-lookup"><span data-stu-id="b1de2-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="b1de2-108">In Ihrem Skype Room System-Administrator Handbuch wird erläutert, wie und wo vertrauenswürdige Domänen im Skype for Business-Client hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b1de2-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="b1de2-109">Nehmen wir beispielsweise an, dass die in Skype for Business Server konfigurierten Zertifikate einen Betreff/Betreff-Alternativnamen von "Contoso" aufweisen. LOCAL "und eine der SIP-Domänen, die einem Benutzer für die Anmeldeadresse des Skype-Chatrooms zugewiesen sind, lautet" confrm1@contoso.net ".</span><span class="sxs-lookup"><span data-stu-id="b1de2-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="b1de2-110">Da contoso.net nicht im Zertifikat vorhanden ist, müssen Sie "contoso. local" auf dem Skype Room-System Computer als vertrauenswürdige Domäne in der Registrierung konfigurieren, wie dies in Ihrem Skype Room System-Administrator Handbuch erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="b1de2-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

