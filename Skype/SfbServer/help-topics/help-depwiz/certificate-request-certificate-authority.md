---
title: Zertifikatsanforderung (Zertifizierungsstelle)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite Zertifizierungsstelle auswählen werden zwei Optionen angezeigt:'
ms.openlocfilehash: 8e070fef17b1577b9a2af72582a51cad564c5551
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911177"
---
# <a name="certificate-request-certificate-authority"></a>Zertifikatsanforderung (Zertifizierungsstelle)
 
Beim Erstellen einer Zertifikatsanforderung an eine Onlinezertifizierungsstelle (im Allgemeinen ein Server im internen Netzwerk) auf der Seite **Zertifizierungsstelle auswählen** werden zwei Optionen angezeigt:
  
1. Wählen Sie eine Zertifizierungsstelle aus der Liste mit den in Ihrer Umgebung erkannten Stellen aus.
    
2. Wählen Sie eine andere Zertifizierungsstelle aus.
    
Wenn Sie die erste Option auswählen, sehen Sie ein Dropdown-Listenfeld, das alle Windows Server-basierten Zertifizierungsstellen enthält, die in Ihrer Umgebung erkannt werden. Wählen Sie die Zertifizierungsstelle, die für das Zertifikat geeignet ist. Möglicherweise müssen den Zertifizierungsstellen-Administrator wissen, welche Zertifizierungsstelle auswählen zu konsultieren.
  
Bei Wahl der zweiten Option geben Sie den vollqualifizierten Domänennamen und die Zertifizierungsstelleninstanz der Zertifizierungsstelle ein, die Sie für das Zertifikat verwenden möchten. Diese Option kommt in Frage, wenn die gewünschte Zertifizierungsstelle keine Windows Server-basierte Zertifizierungsstelle ist, jedoch für Windows Server-basierte Zertifizierungsstellen funktioniert.
  
> [!IMPORTANT]
> Für eine erfolgreiche Zertifikatsanforderung müssen Sie Mitglied der entsprechenden Gruppen sein. Zertifizierungsstellen verfügen normalerweise über eine andere Berechtigung Anforderung die Anforderungen für die Installation von Skype für Business Server auf Servern. Informieren Sie sich über die Voraussetzungen für das Anfordern des Zertifikats bei Ihrem Zertifizierungsstellenadministrator. 
  

