---
title: Zertifikat-Assistent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Im Zertifikat-Assistenten können Sie Zertifikate anfordern, zuweisen, entfernen und anzeigen. Sie müssen als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Wenn Sie ein Zertifikat von der Public Key Infrastructure (PKI) Ihrer Organisation anfordern möchten, müssen Sie überprüfen, welche weiteren Gruppenmitgliedschaften Sie benötigen ( falls möglich). Während der Anforderungsaufgabe können Sie alternative Anmeldeinformationen eingeben, die zum Anfordern des Zertifikats von der ausstellenden Zertifizierungsstelle Ihrer PKI verwendet werden.
ms.openlocfilehash: f8c21cf141d2145e7592a0615a32eafdfa8de10e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805085"
---
# <a name="certificate-wizard"></a>Zertifikat-Assistent
 
Im Zertifikat-Assistenten können Sie Zertifikate anfordern, zuweisen, entfernen und anzeigen. Sie müssen als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein. Zum Anfordern eines Zertifikats von einer öffentlichen Zertifizierungsstelle sind keine besonderen Gruppenmitgliedschaften erforderlich. Wenn Sie ein Zertifikat von der Public Key Infrastructure (PKI) Ihrer Organisation anfordern möchten, müssen Sie überprüfen, welche weiteren Gruppenmitgliedschaften Sie benötigen ( falls möglich). Während der Anforderungsaufgabe können Sie alternative Anmeldeinformationen eingeben, die zum Anfordern des Zertifikats von der ausstellenden Zertifizierungsstelle Ihrer PKI verwendet werden.
  
Klicken Sie zum Anfordern eines neuen Zertifikats auf **Anfordern**.
  
Klicken Sie zum Zuweisen eines noch nicht zugewiesenen Zertifikats auf **Zuweisen**.
  
Klicken Sie zum Entfernen eines bereits zugewiesenen Zertifikats auf **Entfernen**.
  
> [!NOTE]
> Die Schaltfläche **Entfernen** steht nur zur Verfügung, wenn ein Zertifikat zuvor zugewiesen wurde. Ist die Schaltfläche **Entfernen** nicht verfügbar (abgeblendet), wurde kein Zertifikat zugewiesen.
  
Klicken Sie zum Anzeigen eines zugewiesenen Zertifikats auf **Anzeigen**.
  
> [!NOTE]
> Die Schaltfläche **Anzeigen** steht nur zur Verfügung, wenn ein Zertifikat zuvor zugewiesen wurde. Ist die Schaltfläche **Anzeigen** abgeblendet, wurde kein Zertifikat zugewiesen.
  
Klicken Sie zum Aktualisieren des aktuellen Zertifikatzuweisungsbildschirms auf **Aktualisieren**.
  
Klicken Sie zum Importieren eines Zertifikats, das noch nicht im Zertifikatspeicher vorhanden ist, auf **Zertifikat importieren**.
  
> [!NOTE]
> **Das Importzertifikat** wird in der Regel verwendet, um ein Zertifikat zu verarbeiten, das über einen anderen Prozess als eine Anforderung des Zertifikatassistenten empfangen wird. Beispielsweise erstellt ihr PKI-Administrator ein Zertifikat und stellt es Ihnen zur Verfügung. Verwenden **Sie "Zertifikat importieren",** um das Zertifikat in den Zertifikatspeicher des Computers zu importieren und es Skype for Business Server zur Zuweisung zur Verfügung zu stellen.
  
Klicken Sie zum Abschließen der Anforderung eines Zertifikats von einer Zertifizierungsstelle in Ihrer Organisation, für die eine Genehmigung durch den Zertifizierungsstellenadministrator erforderlich ist, auf **Ausstehende Anforderung verarbeiten**. Für die Zertifikatsanforderung wird der Status "Ausstehend" sowie ihre ID-Nummer zurückgegeben. Klicken Sie zum Verarbeiten eines Zertifikats mit ausstehender Genehmigung auf **Aktualisieren**, um die Schaltfläche **Ausstehende Anforderung verarbeiten** zu aktivieren, die danach wieder verfügbar (nicht mehr abgeblendet) ist. Sie können anschließend versuchen, die ausstehende Anforderung abzurufen, doch deren Status bleibt so lange "Ausstehend", bis das Zertifikat vom Zertifizierungsstellenadministrator ausgestellt oder abgelehnt wird. Die Schaltfläche bleibt deaktiviert, wenn es keine gültigen ausstehenden Anforderungen gibt, die mit dem Zertifikat-Assistenten erstellt wurden.
  

