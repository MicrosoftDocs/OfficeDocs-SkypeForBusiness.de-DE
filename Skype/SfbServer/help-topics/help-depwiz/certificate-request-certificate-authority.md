---
title: Zertifikatanforderung (Zertifizierungsstelle)
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
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Wenn Sie eine Zertifikatanforderung an eine Onlinezertifizierungsstelle (in der Regel handelt es sich dabei um Server im internen Netzwerk) auf der Seite "Zertifizierungsstelle auswählen" stellen, werden ihnen zwei Optionen angezeigt:'
ms.openlocfilehash: 0081ab852a1650dfafd61471891a002be60def3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805325"
---
# <a name="certificate-request-certificate-authority"></a>Zertifikatanforderung (Zertifizierungsstelle)
 
Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite **Zertifizierungsstelle auswählen** werden zwei Optionen angezeigt:
  
1. Wählen Sie eine Zertifizierungsstelle aus der Liste mit den in Ihrer Umgebung erkannten Stellen aus.
    
2. Wählen Sie eine andere Zertifizierungsstelle aus.
    
Wenn Sie die erste Option auswählen, wird eine Dropdownliste mit allen Windows Server-basierten Zertifizierungsstellen angezeigt, die in Ihrer Umgebung erkannt werden. Wählen Sie die Zertifizierungsstelle aus, die für Ihr Zertifikat geeignet ist. Möglicherweise müssen Sie sich an Ihren Zertifizierungsstellenadministrator wenden, um zu erfahren, welche Zertifizierungsstelle Sie auswählen sollten.
  
Bei Wahl der zweiten Option geben Sie den vollqualifizierten Domänennamen und die Zertifizierungsstelleninstanz der Zertifizierungsstelle ein, die Sie für das Zertifikat verwenden möchten. Diese Option kommt in Frage, wenn die gewünschte Zertifizierungsstelle keine Windows Server-basierte Zertifizierungsstelle ist, jedoch für Windows Server-basierte Zertifizierungsstellen funktioniert.
  
> [!IMPORTANT]
> Für eine erfolgreiche Zertifikatsanforderung müssen Sie Mitglied der entsprechenden Gruppen sein. In der Regel gelten für Zertifizierungsstellen andere Berechtigungsanforderungen als für die Installation von Skype for Business Server auf Servern. Informieren Sie sich über die Voraussetzungen für das Anfordern des Zertifikats bei Ihrem Zertifizierungsstellenadministrator. 
  

