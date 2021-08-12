---
title: Zertifikatanforderung (Grundlagen)
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
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: Die Seite "Name und Sicherheit" Einstellungen enthält ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bitlänge des privaten und öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen können.
ms.openlocfilehash: a1460f78af07a81b3c02e673a7e81dec0ef0f344987835e4efaadb5309910072
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323277"
---
# <a name="certificate-request-basic"></a>Zertifikatanforderung (Grundlagen)
 
Die Seite **"Name und Sicherheit" Einstellungen** bietet ein Textfeld zum Definieren eines **Anzeigenamens,** eine Dropdownliste für die **Bitlänge** des privaten und öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** können.
  
Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.
  
Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.
  
Wenn Sie das Kontrollkästchen für **den privaten Schlüssel des Zertifikats als exportierbar markieren** aktivieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden. Dies ist nur erforderlich, wenn Sie einen Pool von Edgeservern für den Medienrelay-Authentifizierungsdienst (Media Relay Authentication Service, MRAS) erstellen.
  
> [!CAUTION]
> Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie den privaten Schlüssel des Zertifikats nur dann als exportierbare Option markieren, wenn dies absolut erforderlich ist. 
  

