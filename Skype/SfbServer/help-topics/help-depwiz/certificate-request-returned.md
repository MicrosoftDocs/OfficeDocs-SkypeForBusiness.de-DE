---
title: Zertifikatanforderung (Rückgabe)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/1/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'Die Status der Onlinezertifikatsanforderung Online-Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen. Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert. Standardmäßig ist das Kontrollkästchen weisen dieses Zertifikat Skype für zertifikatverwendungen Business Server aktiviert. Wenn Sie auf "Fertig stellen" klicken, wird das Zertifikat automatisch Lync Server 2013 für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert. Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:'
ms.openlocfilehash: 61e62216cd582a07b95a51d05033482699ca2f3d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201353"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="0cb42-107">Zertifikatanforderung (Rückgabe)</span><span class="sxs-lookup"><span data-stu-id="0cb42-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="0cb42-108">Die **Status der Onlinezertifikatsanforderung Online** -Seite zeigt wichtige Informationen, Ergebnisse aus die erfolgreiche Erstellung und der online zertifikatanforderung ausstellen.</span><span class="sxs-lookup"><span data-stu-id="0cb42-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="0cb42-109">Auf dieser Seite finden den Fingerabdruck des Zertifikats, der das Zertifikat eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0cb42-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="0cb42-110">Standardmäßig ist das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0cb42-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="0cb42-111">Wenn Sie auf **Fertig stellen**klicken, wird das Zertifikat automatisch Lync Server 2013 für die Zwecke zugewiesen werden, die Sie während der Erstellungsschritte zum der zertifikatanforderung definiert.</span><span class="sxs-lookup"><span data-stu-id="0cb42-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="0cb42-112">Standardmäßig sind die Zwecke, die das Zertifikat zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="0cb42-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="0cb42-113">Serverstandard für Transport Layer Security MTLS (Mutual) - Verbindungen mit Clients und anderen Servern</span><span class="sxs-lookup"><span data-stu-id="0cb42-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="0cb42-114">Webdienstintern – Client- und serververbindungen am internen webdienststandort für Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="0cb42-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="0cb42-115">Webdienstextern – Client- und serververbindungen am externen webdienststandort für TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="0cb42-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="0cb42-116">Klicken Sie auf die **Zertifikatdetails Ansicht** zum Anzeigen des Zertifikats, um zu bestätigen, dass die Eigenschaften des Zertifikats sind wie gewünscht und das Zertifikat ist bereit zur angewendet, und platzieren Sie auf dem Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cb42-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="0cb42-117">Klicken Sie auf **Fertig stellen** , um die online zertifikatanforderung ab abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="0cb42-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="0cb42-118">Wenn Sie das Kontrollkästchen **weisen Sie dieses Zertifikat zu Skype für zertifikatverwendungen Business Server**ausgewählt haben, wird das Zertifikat automatisch zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0cb42-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="0cb42-119">Wenn Sie dieses Kontrollkästchen deaktivieren möchten, müssen Sie das Zertifikat in einem separaten Schritt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0cb42-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0cb42-120">Wenn das Stammzertifikat der ausstellenden Zertifizierungsstelle Zertifizierungsstelle (CA) nicht in den Computerspeicher vertrauenswürdige Stammzertifizierungsstelle ist, oder wenn Zertifikate nicht im entsprechenden Store sind, Sie den Status des zusammenfassenden, sehen wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0cb42-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="0cb42-121">Sie haben nicht die Option aus, um das Zertifikat zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0cb42-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="0cb42-122">Um das Zertifikat Zuordnung abzuschließen, müssen Sie importieren Sie das Stammzertifikat der ausstellenden Zertifizierungsstelle und allen Zertifikaten von Zwischenzertifizierungsstellen, und weisen Sie das Zertifikat, indem Sie auf der Hauptseite des Zertifikat-Assistenten auf **zuweisen** .</span><span class="sxs-lookup"><span data-stu-id="0cb42-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

