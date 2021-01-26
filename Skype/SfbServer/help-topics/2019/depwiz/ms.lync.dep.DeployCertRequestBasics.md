---
title: Zertifikatanforderung (Grundlagen)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: Die Seite "Name und Sicherheitseinstellungen" enthält ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bitlänge des Privaten und des öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar markieren können.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830415"
---
# <a name="certificate-request-basic"></a>Zertifikatanforderung (Grundlagen)
 
Die Seite "Name **und Sicherheitseinstellungen"** enthält ein Textfeld zum Definieren  eines Anzeigenamens, eine Dropdownliste für die Bitlänge des Privaten und des öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar markieren **können.**
  
Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.
  
Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.
  
Wenn Sie das Kontrollkästchen aktivieren, um den privaten Schlüssel des Zertifikats als **exportierbar** zu markieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden. Dies ist nur erforderlich, wenn Sie einen Pool von Edgeservern für den Media Relay-Authentifizierungsdienst (Media Relay Authentication Service, MRAS) erstellen.
  
> [!CAUTION]
> Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie den privaten Schlüssel des Zertifikats nur dann als exportierbar markieren, wenn dies unbedingt erforderlich ist. 
  

