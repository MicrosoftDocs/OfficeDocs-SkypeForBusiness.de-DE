---
title: Zertifikat-Assistent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Im Zertifikat-Assistenten können Sie Zertifikate anfordern, zuweisen, entfernenund anzeigen. Sie müssen als Mitglied der Gruppe „RTCUniversalServerAdmins“ angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Wenn Sie ein Zertifikat von der Public Key-Infrastruktur (PKI) Ihrer Organisation anfordern möchten, müssen Sie bestätigen, welche zusätzlichen – wenn überhaupt – Gruppenmitgliedschaften erforderlich sind. Während der Anforderungsaufgabe können Sie alternative Anmeldeinformationen eingeben, die verwendet werden, um das Zertifikat von der ausstellenden Zertifizierungsstelle der PKI anzufordern.
ms.openlocfilehash: 75f324415bbf0af96f79b0e6e5f00e1ee3faaab5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701140"
---
# <a name="certificate-wizard"></a>Zertifikat-Assistent
 
Im Zertifikat-Assistenten können Sie Zertifikate **anfordern**, **zuweisen**, **entfernen**und **anzeigen**. Sie müssen als Mitglied der Gruppe „RTCUniversalServerAdmins“ angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Wenn Sie ein Zertifikat von der Public Key-Infrastruktur (PKI) Ihrer Organisation anfordern möchten, müssen Sie bestätigen, welche zusätzlichen – wenn überhaupt – Gruppenmitgliedschaften erforderlich sind. Während der Anforderungsaufgabe können Sie alternative Anmeldeinformationen eingeben, die verwendet werden, um das Zertifikat von der ausstellenden Zertifizierungsstelle der PKI anzufordern.
  
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
> **Zertifikat importieren** wird in der Regel verwendet, um ein Zertifikat zu verarbeiten, das über einen anderen Prozess als eine Anforderung vom Zertifikat-Assistenten empfangen wird. Beispielsweise erstellt Ihr PKI-Administrator ein Zertifikat und stellt es Ihnen zur Verfügung. Verwenden Sie das Zertifikat **importieren** , um das Zertifikat in den Zertifikatspeicher des Computers zu importieren und dem Skype for Business-Server zur Zuweisung zur Verfügung zu stellen.
  
Wenn Sie den Vorgang zum Anfordern einer Zertifikatanforderung von einer Zertifizierungsstelle in Ihrer Organisation abschließen möchten, die die Genehmigung durch den Zertifizierungsstellenadministrator erfordert, klicken Sie auf **Ausstehend anfordern**. Die Zertifikatanforderung hat den Status Ausstehend zurückgegeben, und es wird auch die Identifikationsnummer der ausstehenden Anforderung angezeigt. Wenn Sie die Verarbeitung eines Zertifikats mit dem Status Ausstehend fortsetzen möchten, klicken Sie auf **Aktualisieren** , um die Schaltfläche **ausstehende Anforderung verarbeiten** zu aktivieren Die Schaltfläche " **ausstehende Anforderung verarbeiten** " ist nicht mehr verfügbar (abgeblendet). Sie können dann versuchen, die ausstehende Anforderung abzurufen, aber der Status der Anforderung bleibt so lange ausstehend, bis das Zertifikat vom Zertifizierungsstellenadministrator ausgestellt oder verweigert wird. Die Schaltfläche ist nicht verfügbar, wenn keine gültigen ausstehenden Anforderungen vorhanden sind, die vom Zertifikat-Assistenten erstellt wurden.
  

