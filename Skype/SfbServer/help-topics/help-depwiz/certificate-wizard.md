---
title: Zertifikat-Assistent
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Im Zertifikat-Assistenten können Sie Zertifikate anfordern, zuweisen, entfernenund anzeigen. Sie müssen als Mitglied der Gruppe „RTCUniversalServerAdmins“ angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Zum Anfordern eines Zertifikats aus Ihrer Organisation public Key-Infrastruktur (PKI), müssen Sie bestätigen was zusätzliche – falls zutreffend – Gruppenmitgliedschaften, die Sie benötigen. Während des Vorgangs Anforderung können Sie alternative Anmeldeinformationen eingeben, die zum anfordern, dass das Zertifikat von Ihrem PKI Zertifizierungsstelle Ausstellen des verwendet werden.
ms.openlocfilehash: 7d20fe489928a430c972c7e48e0938ff1eb1622d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220445"
---
# <a name="certificate-wizard"></a>Zertifikat-Assistent
 
Im Zertifikat-Assistenten können Sie Zertifikate **anfordern**, **zuweisen**, **entfernen**und **anzeigen**. Sie müssen als Mitglied der Gruppe „RTCUniversalServerAdmins“ angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Zum Anfordern eines Zertifikats aus Ihrer Organisation public Key-Infrastruktur (PKI), müssen Sie bestätigen was zusätzliche – falls zutreffend – Gruppenmitgliedschaften, die Sie benötigen. Während des Vorgangs Anforderung können Sie alternative Anmeldeinformationen eingeben, die zum anfordern, dass das Zertifikat von Ihrem PKI Zertifizierungsstelle Ausstellen des verwendet werden.
  
Klicken Sie zum Anfordern eines neuen Zertifikats auf **Anfordern**.
  
Klicken Sie zum Zuweisen eines noch nicht zugewiesenen Zertifikats auf **Zuweisen**.
  
Klicken Sie zum Entfernen eines bereits zugewiesenen Zertifikats auf **Entfernen**.
  
> [!NOTE]
> Die Schaltfläche **Entfernen** steht nur zur Verfügung, wenn zuvor ein Zertifikat zugewiesen wurde. Wenn die Schaltfläche **Entfernen** nicht verfügbar (abgeblendet) ist, wurde kein Zertifikat zugewiesen.
  
Klicken Sie zum Anzeigen eines zugewiesenen Zertifikats auf **Anzeigen**.
  
> [!NOTE]
> Die Schaltfläche **Anzeigen** steht nur zur Verfügung, wenn zuvor ein Zertifikat zugewiesen wurde. Wenn die Schaltfläche **Anzeigen** abgeblendet ist, wurde kein Zertifikat zugewiesen.
  
Klicken Sie zum Aktualisieren des aktuellen Zertifikatzuweisungsbildschirms auf **Aktualisieren**.
  
Klicken Sie zum Importieren eines Zertifikats, das noch nicht im Zertifikatspeicher vorhanden ist, auf **Zertifikat importieren**.
  
> [!NOTE]
> **Importieren des Zertifikats** wird normalerweise verwendet, um ein Zertifikat verarbeiten, die über einen anderen Prozess als einer Anforderung in den Zertifikat-Assistenten empfangen wird. Beispiel der PKI-Administrator erstellt ein Zertifikat und für Sie verfügbar gemacht. **Zertifikat importieren** zum Importieren des Zertifikats in Zertifikat des Computers speichern und zur Verfügung gestellt Skype für Business Server zuweisen.
  
To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.
  

