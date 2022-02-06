---
title: Planen der Remoteanrufsteuerung in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 'Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellenanlagentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Über Arbeit anrufen" ersetzt. In den Clientversionen für Skype for Business Server 2015 und in Zukunft ist die Remoteanrufsteuerung im Client nicht mehr verfügbar und wurde zur Verwendung entfernt.'
---

# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planen der Remoteanrufsteuerung in Skype for Business
 
Die Remoteanrufsteuerung war in früheren Versionen von Lync Server ein Feature, mit dem Benutzer ihre Nebenstellenanlagentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Über Arbeit anrufen" ersetzt.  *In den Clientversionen für Skype for Business Server 2015 und in Zukunft ist die Remoteanrufsteuerung im Client nicht mehr verfügbar und wurde zur Verwendung entfernt.* 
  
 Benutzer der Remoteanrufsteuerung in Ihrer Organisation, die auf Front-End-Servern mit Lync Server verwaltet werden, können weiterhin die Remoteanrufsteuerung verwenden, auch wenn sie einen Skype for Business-Client verwenden. Für Benutzer, die auf Skype for Business Server verwaltet werden, wird die Remoteanrufsteuerung jedoch nicht unterstützt. In der folgenden Tabelle finden Sie Server-/Clientkombinationen und informationen dazu, ob sie die Remoteanrufsteuerung oder "Anruf über Arbeit" unterstützen können.
  
|&nbsp;|Skype for Business Client mit aktivierter Skype Benutzeroberfläche|Skype for Business Client mit aktivierter Lync-Benutzeroberfläche|Skype for Business 2016-Client|Lync 2013-Client|Lync 2010-Client|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server  |Anruf über den Arbeitsplatz   |1  |Anruf über den Arbeitsplatz   |1  |1  |
| Lync Server 2013  |Remoteanrufsteuerung   |Remoteanrufsteuerung   |1  |Remoteanrufsteuerung   |Remoteanrufsteuerung   |
| Lync Server 2010  |Remoteanrufsteuerung   |Remoteanrufsteuerung   |1  |Remoteanrufsteuerung   |Remoteanrufsteuerung   |
   
1. Keines der Features wird unterstützt.
  
Weitere Informationen finden Sie in der Dokumentation [zur Remoteanrufsteuerung](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in Lync Server 2013.
  
## <a name="see-also"></a>Siehe auch

[Plan for Call Via Work in Skype for Business Server](call-via-work.md)
  
[Vergleich der Desktopclientfeatures für Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Tätigen eines Skype for Business Anrufs, aber verwenden Sie Ihr Festnetztelefon für Audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)