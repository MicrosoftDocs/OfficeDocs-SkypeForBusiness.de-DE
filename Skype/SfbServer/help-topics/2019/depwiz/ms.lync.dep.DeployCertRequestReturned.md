---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'Auf der Status Seite "Online Zertifikatanforderung" werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben. Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen Dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen ausgewählt. Wenn Sie auf Fertig stellen klicken, wird das Zertifikat automatisch dem Skype for Business-Server für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben. Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:'
ms.openlocfilehash: 1fce25992e6509fe10715f80f4121e08c6734be2
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794294"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="f42b5-107">Zertifikatanforderung (Rückgabe)</span><span class="sxs-lookup"><span data-stu-id="f42b5-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="f42b5-108">Auf der Status Seite " **Online Zertifikatanforderung** " werden wichtige Informationen angezeigt, die sich aus der erfolgreichen Erstellung und Ausgabe der Online Zertifikatanforderung ergeben.</span><span class="sxs-lookup"><span data-stu-id="f42b5-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="f42b5-109">Diese Seite enthält den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f42b5-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="f42b5-110">Standardmäßig ist das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="f42b5-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="f42b5-111">Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch dem Skype for Business-Server für die Zwecke zugewiesen, die Sie während der Erstellungsschritte der Zertifikatanforderung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="f42b5-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="f42b5-112">Standardmäßig werden die Zwecke, denen das Zertifikat zugewiesen wird, wie folgt festgelegt:</span><span class="sxs-lookup"><span data-stu-id="f42b5-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="f42b5-113">Server Standard für MTLS (Mutual Transport Layer Security) – Verbindungen zu Clients und anderen Servern</span><span class="sxs-lookup"><span data-stu-id="f42b5-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="f42b5-114">Web Services Internal-Client-und Serververbindungen auf der internen Webdienste-Website für Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="f42b5-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="f42b5-115">Web Services External-Client-und Serververbindungen auf der externen Webdienste-Website für TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="f42b5-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="f42b5-116">Klicken Sie auf die Details des Zertifikats **anzeigen** , um das Zertifikat anzuzeigen, um zu bestätigen, dass die Eigenschaften des Zertifikats dem entsprechen, was Sie beabsichtigt haben, und dass das Zertifikat auf dem Server angewendet und verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f42b5-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="f42b5-117">Klicken Sie auf **Fertig stellen** , um den Online Zertifikat Anforderungsprozess abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f42b5-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="f42b5-118">Wenn Sie das Kontrollkästchen **dieses Zertifikat den Skype for Business Server-Zertifikat Verwendungen zuweisen**aktiviert haben, wird das Zertifikat automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f42b5-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="f42b5-119">Wenn Sie dieses Kontrollkästchen deaktiviert haben, müssen Sie das Zertifikat in einem separaten Schritt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f42b5-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f42b5-120">Wenn sich das Stammzertifikat der ausstellenden Zertifizierungsstelle nicht im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Computers befindet oder wenn sich Zwischenzertifizierungsstellen Zertifikate nicht im richtigen Speicher befinden, wird der Zusammenfassungsstatus angezeigt, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f42b5-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="f42b5-121">Sie haben nicht die Möglichkeit, das Zertifikat zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f42b5-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="f42b5-122">Zum Abschließen des Zertifikats Zuordnungsprozesses müssen Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und alle Zwischenzertifizierungsstellen Zertifikate importieren und dann das Zertifikat zuweisen, indem Sie auf der Seite Hauptzertifikat-Assistent auf **zuweisen** klicken.</span><span class="sxs-lookup"><span data-stu-id="f42b5-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

