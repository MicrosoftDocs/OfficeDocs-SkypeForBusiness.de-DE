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
description: Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Anruf über Arbeit" ersetzt. In den Clientversionen für Skype for Business Server 2015 und in Zukunft ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114611"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planen der Remoteanrufsteuerung in Skype for Business
 
Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Anruf über Arbeit" ersetzt.  *In den Clientversionen für Skype for Business Server 2015 und in Zukunft ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.* 
  
 Remoteanrufsteuerungsbenutzer in Ihrer Organisation, die auf Front-End-Servern mit Lync Server gespeichert sind, können weiterhin die Remoteanrufsteuerung verwenden, auch wenn sie einen Skype for Business-Client verwenden. Für alle Benutzer, die in Skype for Business Server gespeichert sind, wird die Remoteanrufsteuerung jedoch nicht unterstützt. In der folgenden Tabelle finden Sie Server-Client-Kombinationen, und ob sie die Remoteanrufsteuerung oder die Anrufsteuerung über die Arbeit unterstützen können.
  
||**Skype for Business-Client mit aktivierter Skype-UI**|**Skype for Business-Client mit aktivierter Lync-Benutzeroberfläche**|**Skype for Business 2016 Client**|**Lync 2013-Client**|**Lync 2010-Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Anruf über den Arbeitsplatz  <br/> |1 <br/> |Anruf über den Arbeitsplatz  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |1 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |
| Lync Server 2010 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |1 <br/> |Remoteanrufsteuerung  <br/> |Remoteanrufsteuerung  <br/> |
   
1. Keines der Features wird unterstützt.
  
Weitere Informationen finden Sie unter [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in der Lync Server 2013-Dokumentation.
  
## <a name="see-also"></a>Siehe auch

[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[Vergleich der Desktopclientfeatures für Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Führen Sie einen Skype for Business-Anruf aus, verwenden Sie aber Ihr Nebenstellentelefon für Audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)