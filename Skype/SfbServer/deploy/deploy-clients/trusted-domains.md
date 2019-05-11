---
title: Skype Room System – Vertrauenswürdige Domänen
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.
ms.openlocfilehash: ff8f75178fef21900292760fb71f53ea3746380c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895047"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="7cc9f-103">Skype Room System – Vertrauenswürdige Domänen</span><span class="sxs-lookup"><span data-stu-id="7cc9f-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="7cc9f-104">Lesen Sie dieses Thema und erfahren Sie, wie Sie vertrauenswürdige Domänen für Skype Room System und Skype for Business konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7cc9f-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="7cc9f-105">Vertrauenswürdige Domänen</span><span class="sxs-lookup"><span data-stu-id="7cc9f-105">Trusted domains</span></span>

<span data-ttu-id="7cc9f-106">Die Skype für Business Client zeigt ein Dialogfeld, mit dem Benutzer das Zertifikat aus der Skype für Business Server akzeptiert, wenn die SIP-Domäne des Benutzerkontos anmelden den Namen des Zertifikats im Betreff oder Antragstellername Alt präsentiert abweicht.</span><span class="sxs-lookup"><span data-stu-id="7cc9f-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="7cc9f-107">Wenn das Zertifikat für Skype für Business Server in Ihrer Organisation konfigurierten keinen SIP-Domänenname des Skype Raum Systemkonto im Betreff oder Alt Antragstellername, müssen Sie diese Domänen auf das Zertifikat unter Vertrauenswürdige Domänen präsentiert konfigurieren. Registrierungsschlüssel auf dem Computer des Skype Raum System-Konsole.</span><span class="sxs-lookup"><span data-stu-id="7cc9f-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="7cc9f-108">Skype Raum System Hersteller bereitgestellten Skype Raum vom Systemadministrator Handbuch wird erläutert, wie und wo in der Skype für Business Client vertrauenswürdigen Domänen hinzu.</span><span class="sxs-lookup"><span data-stu-id="7cc9f-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="7cc9f-109">Nehmen wir beispielsweise an, dass die Zertifikate auf Skype für Business Server konfigurierten Betreff/Alt Antragstellernamen "CONTOSO. verfügen LOCAL"und eine der SIP-Domänen, die einem Benutzer für die Skype Raum System Anmeldeadresse zugewiesen ist"confrm1@contoso.net."</span><span class="sxs-lookup"><span data-stu-id="7cc9f-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="7cc9f-110">Da contoso.net nicht in das Zertifikat auf dem Computer Skype Raum System ist, müssen Sie "contoso.local" als vertrauenswürdige Domäne in der Registrierung konfigurieren, wie in Ihrer Skype Raum System Hersteller bereitgestellten Skype Raum System-Administratorhandbuch erläutert.</span><span class="sxs-lookup"><span data-stu-id="7cc9f-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

