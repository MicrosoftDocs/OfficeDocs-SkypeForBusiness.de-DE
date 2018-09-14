---
title: Skype für Unternehmen auf Mac-Clientanforderungen
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Dieses Thema bietet Informationen zu Hardware-, Software- und infrastrukturanforderungen für die Ausführung von Skype für Unternehmen auf einem Mac
ms.openlocfilehash: 694f64933f4618b5c2157f7a35acdf9339d52919
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965627"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype für Unternehmen auf Mac-Clientanforderungen
 
Dieses Thema bietet Informationen zu Hardware-, Software- und infrastrukturanforderungen für die Ausführung von Skype für Unternehmen auf einem Mac
  
Die [Skype für Unternehmen auf dem Mac-Client](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) ist zum Download zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-the-mac"></a>Hardware- und Softwareanforderungen für Skype for Business auf dem Mac

Die Skype für Unternehmen auf dem Mac-Client erfordert Mac OS X El Capitan und höher und mindestens 100MB freier Speicherplatz verwendet. Die Verwendung aller integrierten Audio- und Videogeräte wird unterstützt. Externe Geräte muss in der [Skype für Geschäftsdatenkatalog-Lösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog). 
  
> [!NOTE]
> Diese Liste ist vorläufig und einige Geräte möglicherweise für Lync qualifizierte, jedoch nicht unterstützt Skype für Unternehmen unter Mac. Verweisen Sie auf die [Systemanforderungen](https://products.office.com/en-us/office-system-requirements) für die Mindestanforderungen an die Hardware erforderlich.
  
### <a name="legacy-mac-clients"></a>Mac-Legacyclients

Skype für Business Server 2015 unterstützt die folgenden Clients von Vorversionen auch auf Computern, die ausgeführt werden, Mac OS 10.5.8 oder neuestes Servicepack oder release (Intel-basiert) Betriebssysteme (Mac OS 10.9 Betriebssystem wird derzeit nicht unterstützt). Ausführliche Informationen zu unterstützten Funktionen finden Sie unter [Desktopclient Featurevergleich für Skype für Unternehmen](desktop-feature-comparison.md).
  
- Microsoft Lync für Mac 2011 (siehe [Lync für Mac 2011 – Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator für Mac 2011 (siehe [Communicator für Mac 2011 – Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Diese Clients werden durch Skype für Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-the-mac"></a>Infrastrukturanforderungen für Skype for Business auf dem Mac
<a name="Infrastructure"> </a>

Die Skype für Unternehmen auf dem Mac-Client nutzt sowohl die Unified Communications-Management-Plattform (UCMP) als auch die Unified Communications Web-API (UCWA), die unsere Mobilität Clients verwenden.
  
Für den Client gelten die gleichen Anforderungen wie bei unseren Mobilitätsclients in der Hinsicht, dass Sie einen Zugriffs-Edgeserver und Reverseproxy in einer unterstützten Konfiguration bereitstellen müssen. 
  
### <a name="authentication"></a>Authentifizierung

Die Skype für Unternehmen auf dem Mac-Client unterstützt Cert-basierte Authentifizierung, moderne Microsoft-Authentifizierung und mehrstufige Authentifizierung, wenn bereitgestellt und aktiviert.
  
> [!NOTE]
> Aufgrund der aktuellen Beschränkung müssen die Anmeldeinformationen des Benutzers Exchange die ihre Skype Business Anmeldeinformationen für identisch sein. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf den Zugriffs-Edge-, Reverseproxy- und Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die HTTP-Zertifikatsperrliste muss definiert und für den Client zugänglich sein. Beispielsweise unterstützen nicht wir einen LDAP-Eintrag in das Zertifikat als Ihrer Certificate Revocation List.
  
### <a name="dns"></a>DNS

Mobilität muss auf dem Client Mac ordnungsgemäß funktioniert ordnungsgemäß für die Skype für Unternehmen bereitgestellt werden. Ein typisches Fehlerszenario wäre es, wenn im internen Netzwerk die folgenden beiden DNS-Einträge aufgelöst werden können:
  
- Lyncdiscoverinternal. \<Sipdomain\>
    
- Lyncdiscover. \<Sipdomain\>
    
Weitere Informationen finden Sie unter: [Bereitstellen von Mobilität in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)und [Microsoft Lync Server 2010-Mobilitätshandbuch](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype für Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)