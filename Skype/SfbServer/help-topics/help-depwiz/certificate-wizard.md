---
title: Zertifikat-Assistent
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
description: Um anzufordern, zuweisen möchten, entfernen oder Zertifikate anzuzeigen, verwenden Sie den Zertifikat-Assistenten. Sie müssen als Mitglied der Gruppe „RTCUniversalServerAdmins“ angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Zum Anfordern eines Zertifikats aus Ihrer Organisation public Key-Infrastruktur (PKI), müssen Sie bestätigen was zusätzliche – falls zutreffend – Gruppenmitgliedschaften, die Sie benötigen. Während des Vorgangs Anforderung können Sie alternative Anmeldeinformationen eingeben, die zum anfordern, dass das Zertifikat von Ihrem PKI Zertifizierungsstelle Ausstellen des verwendet werden.
ms.openlocfilehash: d700a6cae510bbc12ed2e37c9c3df166d2704269
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
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
  
Zum Abschließen des Prozess des Anforderns von einer Anforderung von einer Zertifizierungsstelle in Ihrer Organisation, die Zertifizierungsstelle Administrator genehmigt werden muss, klicken Sie auf **Ausstehende Anforderung Prozess**. Die Anforderung wird der Status pending zurückgegeben haben, und zeigt auch die Kennnummer des ausstehende Anforderung. Klicken Sie auf **Aktualisieren** , um die Schaltfläche **Prozess ausstehende Anforderung** zu aktivieren, um den Vorgang fortzusetzen, ein Zertifikat mit dem Status ausstehende Verarbeitung. Die Schaltfläche **Prozess ausstehende Anforderung** werden nicht mehr verfügbar (abgeblendet). Sie können dann versuchen, die ausstehende Anforderung abrufen, jedoch bleibt des Status der Anforderung offen, bis das Zertifikat ausgestellt oder vom Administrator Zertifizierungsstelle verweigert. Die Schaltfläche ist nicht verfügbar, wenn es sind keine gültigen ausstehender Anfragen, die mit dem Zertifikat-Assistenten erstellt wurden.
  

