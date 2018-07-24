---
title: Zertifikatliste
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn Sie ein Zertifikat zuweisen möchten, wählen Sie im lokalen Zertifikatspeicher ein Zertifikat aus. Klicken Sie auf Weiter, um den Vorgang fortzusetzen.
ms.openlocfilehash: 62dcc2abfde1d2216288b8137a9ab2a2448d5404
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987479"
---
# <a name="certificate-list"></a><span data-ttu-id="22963-104">Zertifikatliste</span><span class="sxs-lookup"><span data-stu-id="22963-104">Certificate List</span></span>
 
<span data-ttu-id="22963-p102">Wenn Sie ein Zertifikat zuweisen möchten, wählen Sie im lokalen Zertifikatspeicher ein Zertifikat aus. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="22963-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="22963-p103">Die Zertifikate im Bereich **Zertifikat aus dem lokalen Zertifikatspeicher auswählen** sind gültige Zertifikate, die für den jeweiligen Zweck zugewiesen werden können. Klicken Sie auf die Schaltfläche **Zertifikatdetails anzeigen**, um zu prüfen, ob das ausgewählte Zertifikat das richtige Zertifikat ist. Die Registerkarte **Details** enthält den für das Zertifikat konfigurierten Antragstellernamen und alternative Antragstellernamen.</span><span class="sxs-lookup"><span data-stu-id="22963-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="22963-p104">Möglicherweise wird im Auswahlbereich kein Zertifikat angezeigt. Die häufigste Ursache hierfür ist, dass auf dem vorgesehenen Server kein vertrauenswürdiges Stammzertifikat vorhanden ist bzw. keine Zertifikate von Zwischenzertifizierungsstellen installiert sind, um das Zertifikat zu bestätigen und so die Vertrauenskette aufrechtzuerhalten, die durch das Zertifikat seitens der Zertifizierungsstelle eingerichtet wurde. Lösen Sie dieses Problem, indem Sie eine Zertifikatkette anfordern und importieren. Meist umfasst diese das Zertifikat der Stammzertifizierungsstelle sowie Zertifikate von Zwischenzertifizierungsstellen und ausstellenden Zertifizierungsstellen.</span><span class="sxs-lookup"><span data-stu-id="22963-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

