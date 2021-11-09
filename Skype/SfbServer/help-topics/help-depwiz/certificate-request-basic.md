---
title: Zertifikatanforderung (Grundlagen)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
description: Die Seite "Name und Sicherheit" Einstellungen bietet ein Textfeld zum Definieren eines Anzeigenamens, eine Dropdownliste für die Bitlänge des privaten und öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen können.
ms.openlocfilehash: dcb26b7ffe310b593d5e73e6602551c98cf1eb2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865002"
---
# <a name="certificate-request-basic"></a>Zertifikatanforderung (Grundlagen)
 
Die Seite **"Name und Sicherheit" Einstellungen** bietet ein Textfeld zum Definieren eines **Anzeigenamens,** eine Dropdownliste für die **Bitlänge** des privaten und öffentlichen Schlüsselpaars sowie ein Kontrollkästchen, mit dem Sie **den privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** können.
  
Beim Anzeigenamen (oder einfachen Namen) eines Zertifikats handelt es sich um einen benutzerfreundlichen und problemlos identifizierbaren Namen für den Benutzer, der das Zertifikat anzeigt.
  
Für die Bitlänge des öffentlich-privaten Schlüsselpaars kann der Wert 1024, 2048 oder 4096 festgelegt werden.
  
Wenn Sie das Kontrollkästchen für **den privaten Schlüssel des Zertifikats als exportierbar markieren** aktivieren, können das Zertifikat und der private Schlüssel exportiert und auf einen anderen Computer oder Server verschoben werden. Dies ist nur erforderlich, wenn Sie einen Pool von Edgeservern für den Medienrelay-Authentifizierungsdienst (Media Relay Authentication Service, MRAS) erstellen.
  
> [!CAUTION]
> Um die Sicherheit des Zertifikats und des Schlüsselpaars zu gewährleisten, sollten Sie den privaten Schlüssel des Zertifikats nur dann als exportierbare Option markieren, wenn dies absolut erforderlich ist. 
  

