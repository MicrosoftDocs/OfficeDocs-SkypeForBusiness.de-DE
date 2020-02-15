---
title: Planen der Remoteanrufsteuerung in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Die Remote Anrufsteuerung war ein Feature in früheren Versionen von lync Server, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch die Funktion "Anruf über Arbeit" ersetzt. In den Clientversionen für Skype for Business Server 2015 und weiterleiten ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982800"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planen der Remoteanrufsteuerung in Skype for Business
 
Die Remote Anrufsteuerung war ein Feature in früheren Versionen von lync Server, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch die Funktion "Anruf über Arbeit" ersetzt.  *In den Clientversionen für Skype for Business Server 2015 und weiterleiten ist die Remoteanrufsteuerung nicht mehr für die Konfiguration im Client verfügbar und wurde zur Verwendung entfernt.* 
  
 Remoteanrufsteuerung Benutzer in Ihrer Organisation, die auf Front-End-Servern mit lync Server verwaltet werden, können die Remoteanrufsteuerung auch dann weiterhin verwenden, wenn Sie einen Skype for Business-Client verwenden. Für Benutzer, die in Skype for Business Server verwaltet werden, wird die Remoteanrufsteuerung jedoch nicht unterstützt. In der folgenden Tabelle finden Sie eine Kombination aus Server-und Client Kombinationen sowie Informationen dazu, ob Sie die Remoteanrufsteuerung oder den Anruf über Arbeit unterstützen können.
  
||**Skype for Business Client mit aktivierter Skype-Benutzeroberfläche**|**Skype for Business Client mit aktivierter lync-Benutzeroberfläche**|**Skype for Business 2016-Client**|**Lync 2013-Client**|**Lync 2010-Client**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype for Business Server <br/> |Anruf über den Arbeitsplatz  <br/> |1  <br/> |Anruf über den Arbeitsplatz  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Remote Anrufsteuerung  <br/> |Remote Anrufsteuerung  <br/> |1  <br/> |Remote Anrufsteuerung  <br/> |Remote Anrufsteuerung  <br/> |
| Lync Server 2010 <br/> |Remote Anrufsteuerung  <br/> |Remote Anrufsteuerung  <br/> |1  <br/> |Remote Anrufsteuerung  <br/> |Remote Anrufsteuerung  <br/> |
   
1. Keine Funktion wird unterstützt.
  
Weitere Informationen finden Sie unter [Remote Anrufsteuerung](https://go.microsoft.com/fwlink/p/?LinkId=530208) in der lync Server 2013 Dokumentation.
  
## <a name="see-also"></a>Siehe auch

[Planen der Anruf über Arbeit in Skype for Business Server](call-via-work.md)
  
[Vergleich der Desktop Clientfeatures für Skype for Business](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Einen Skype for Business Anruf tätigen, aber Ihr PBX-Telefon für Audio verwenden](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

