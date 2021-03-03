---
title: Planen der Remoteanrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde diese Funktion durch "Geschäft arbeitsplatz" ersetzt. In den Clientversionen für Skype for Business Server 2015 und in Zukunft steht die Remoteanrufsteuerung nicht mehr zur Konfiguration im Client zur Verfügung und wurde für die Verwendung entfernt.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813515"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planen der Remoteanrufsteuerung in Skype for Business
 
Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde diese Funktion durch "Geschäft arbeitsplatz" ersetzt.  *In den Clientversionen für Skype for Business Server 2015 und in Zukunft steht die Remoteanrufsteuerung nicht mehr zur Konfiguration im Client zur Verfügung und wurde für die Verwendung entfernt.* 
  
 Benutzer der Remoteanrufsteuerung in Ihrer Organisation, die auf Front-End-Servern mit Lync Server gespeichert sind, können die Remoteanrufsteuerung auch dann weiterhin verwenden, wenn sie einen Skype for Business-Client verwenden. Für Benutzer, die in Skype for Business Server gespeichert sind, wird die Remoteanrufsteuerung jedoch nicht unterstützt. In der folgenden Tabelle finden Sie Server-Client-Kombinationen und informationen dazu, ob sie die Remoteanrufsteuerung oder "Anruf über Arbeit" unterstützen können.
  
||**Skype for Business Client mit aktivierter Skype-UI**|**Skype for Business Client mit aktivierter Lync-Benutzeroberfläche**|**Skype for Business 2016 Client**|**Lync 2013-Client**|**Lync 2010-Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Anruf über den Arbeitsplatz  <br/> |1  <br/> |Anruf über den Arbeitsplatz  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |1  <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |
| Lync Server 2010 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |1  <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |
   
1. Keines dieser Features wird unterstützt.
  
Weitere Informationen finden Sie unter ["Remoteanrufsteuerung"](https://go.microsoft.com/fwlink/p/?LinkId=530208) in der Lync Server 2013-Dokumentation.
  
## <a name="see-also"></a>Weitere Informationen

[Planen der Anruf-über-Arbeit in Skype for Business Server](call-via-work.md)
  
[Vergleich der Desktopclientfeatures für Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Führen Sie einen Skype for Business-Anruf, aber verwenden Sie Ihr Nebenstellentelefon für Audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

