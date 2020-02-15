---
title: Skype for Business Topologien, die mit moderner Authentifizierung unterstützt werden
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
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: In diesem Artikel wird aufgeführt, welche Online-und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für die einzelnen Topologien gelten.
ms.openlocfilehash: b23c2081833b43f0f734febc0b18356abf63506e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043757"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Skype for Business Topologien, die mit moderner Authentifizierung unterstützt werden
 
In diesem Artikel wird aufgeführt, welche Online-und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für die einzelnen Topologien gelten.
  
## <a name="modern-authentication-in-skype-for-business"></a>Moderne Authentifizierung in Skype for Business

Skype for Business können die Sicherheitsvorteile der modernen Authentifizierung nutzen. Da Skype for Business eng mit Exchange zusammenarbeitet, wird das Anmeldeverhalten Skype for Business Client Benutzern angezeigt, auch durch den MA-Status von Exchange beeinflusst. Dies gilt auch dann, wenn Sie über eine Skype for Business geteilte Domänen-Hybridlösung verfügen. Das sind viele bewegliche Teile, aber das Ziel ist eine einfach zu veranschaulichende Liste der unterstützten Topologien.
  
Welche Topologien werden mit MA Skype for Business, Skype for Business Online, Exchange Server und Exchange Online unterstützt?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Unterstützte MA-Topologien in Skype for Business

Es gibt potenziell zwei Serveranwendungen und zwei Office 365 Arbeitsauslastungen, die mit Skype for Business von Ma verwendeten Topologien in Zusammenhangstehen.
  
- Lokale Skype for Business Server (Cu 5)
    
- Skype for Business Online (SFBO)
    
- Lokale Exchange-Server
    
- Exchange Server Online (Exo)
    
Ein weiterer wichtiger Teil von Ma besteht darin zu wissen, wo die Authentifizierung (authn) und die Autorisierung (authZ) von Benutzern stattfinden. Die beiden Optionen sind:
  
- Azure AD, Online in der Microsoft-Cloud
    
- Lokale Active Directory Verbund Server (AD FS)
    
So sieht es ein bisschen so aus: mit Exo und SFBO in der Cloud mit Azure AD und Exchange Server ($) und Skype for Business Server (SFB) auf-Prem.
  
![Ein Beispiel für alle Anwendungen (Exchange und Skype for Business) und Arbeitsauslastungen (Exo und SFBO) und die beiden autorisierungsserver (ADFS und evoSTS), die beim Aktivieren von Ma beteiligt sein können.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Hier sind die unterstützten Topologien. Beachten Sie den Schlüssel für die Grafiken:
  
- Wenn das Symbol abgeblendet oder grau ist, wird es im Szenario nicht verwendet.
    
- Exo ist Exchange Online.
    
- SFBO ist Skype for Business Online.
    
- Wechsel erfolgt lokal.
    
- SFB ist Skype for Business lokal.
    
- Das Autorisieren von Servern wird durch Dreiecke dargestellt, beispielsweise ist das Azure AD ein Dreieck mit einer Wolke dahinter.
    
- Pfeile zeigen auf den autorisierungsserver, der verwendet wird, wenn Clients versuchen, die angegebene Server Ressource zu erreichen.
    
Lassen Sie uns zunächst MA mit Skype for Business sowohl in lokalen als auch in reinen Cloud-Topologien abdecken.
  
> [!IMPORTANT]
> Sind Sie für die Einrichtung der modernen Authentifizierung in Skype for Business Online gerüstet? Die Schritte zum Aktivieren dieses Features sind [hier](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)genau richtig. 
  
|Name der Topologie  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Nur für die Cloud  <br/> |![Unterstützte SFB mit MA-Topologie, nur Cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Verwaltete Benutzer/Postfächer: Online  <br/> |MA ist sowohl für Exo als auch für SFBO.  <br/> Daher ist der autorisierungsserver Azure AD.  <br/> |Mehrstufige Authentifizierung (MFA), Client-Zertifikat-basierte Authentifizierung (CBA), bedingter Zugriff (ca)/Mobile-Faltblatt Application Management (MAM) mit InTune. \*  <br/> |
|Nur on-Prem  <br/> |![Unterstützte SFB mit MA-Topologie, nur lokal.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Verwaltete Benutzer/Postfächer, die sich befinden: lokal  <br/> |MA ist für SFB lokal eingeschaltet.  <br/> Daher ist der autorisierungsserver ADFS.  <br/> Konfigurationsdetails finden Sie in [diesem Artikel.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (nur Windows-Desktop – Mobile Clients werden nicht unterstützt). Keine Exchange-Integrationsfeatures.  <br/><p> **Diese Vorgehensweise wird nicht empfohlen. Weitere Informationen finden Sie hier:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> Es wird empfohlen, dass der MA-Status für Skype for Business und Exchange (und Ihre Online-Gegenparts) gleich ist, um die Anzahl der Eingabeaufforderungen zu verringern. 
  
Gemischte Topologien beinhalten Kombinationen von SFB-Hybriden mit geteilter Domäne. Dabei handelt es sich um die derzeit unterstützten gemischten Topologien:
  
|Name der Topologie  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Gemischt 1  <br/> |![Unterstützte SFB mit MA-Topologie, Mixed 1 (Exo + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Verwaltete Benutzer/Postfächer: Exo und SFB  <br/> |MA ist für SFB nicht aktiviert; in dieser Topologie sind keine SFB-MA-Funktionen verfügbar.  <br/> |Keine Ma-Funktionen für SFB.  <br/> |
|Gemischt 2  <br/> |![Unterstützte MA mit Skype for Business gemischten Topologie 2, SFBO Plus MA, die mit Wechsel auf-Prem arbeitet.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Verwaltete Benutzer/Postfächer: Kursund SFBO  <br/> |MA ist nur für SFBO. Der autorisierungsserver ist für Benutzer, die in SFBO verwaltet werden, Azure AD, aber AD für lokale Abschaltung.  <br/> |MFA, CBA, ca/MAM mit InTune.\*  <br/> |
|Gemischt 3  <br/> |![Unterstützte MA mit SFB, Exo mit MA on, plus-und SFB vor Ort.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Verwaltete Benutzer/Postfächer: Exo + SFB oder intersfb  <br/> |In dieser Topologie sind keine SFB-MA-Funktionen verfügbar.  <br/> |Keine Ma-Funktionen für SFB.  <br/> |
|Gemischt 4  <br/> |![Unterstützte MA mit SFB, SFBO mit MA on, plus-und SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Verwaltete Benutzer/Postfächer: "$ + SFBO" oder "$ + SFB"  <br/> |MA ist für SFBO eingeschaltet, daher ist der autorisierungsserver für Benutzer Azure AD, die in SFBO verwaltet werden. Benutzer von "on-Prem" in SFB und Exo verwenden AD.  <br/> |MFA, CBA, ca/MAM mit InTune nur für Online-Benutzer.\*  <br/> |
|Gemischt 5  <br/> |![Unterstützte MA in SFB, Exo mit MA und SFBO mit MA sowie mit dem Studien-und SFB vor Ort.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Verwaltete Benutzer/Postfächer: Exo + SFBO, Exo + SFB, interSFBO oder intersfb  <br/> |MA ist sowohl in Exo als auch in SFBO, daher ist der autorisierungsserver für Benutzer Azure AD, die in SFBO verwaltet werden; Benutzer von "on-Prem" in "in" und "SFB" verwenden AD.  <br/> |MFA, CBA, ca/MAM mit InTune nur für Online-Benutzer.\*  <br/> |
|Gemischt 6  <br/> |![In einer gemischten 6-Topologie befindet sich die moderne Authentifizierung an allen vier possibile-Standorten – die ideale Situation im Hinblick auf moderne auth-Typen.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Verwaltete Benutzer/Postfächer: Exo + SFBO, Exo + SFB, interSFBO oder intersfb  <br/> |MA ist überall, daher ist der autorisierungsserver für alle Benutzer Azure AD. (Online und lokal)  <br/>  Weitere Informationen [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) finden Sie unter Bereitstellungsschritte. <br/> |MFA, CBA und ca/MAM (über InTune) für alle Benutzer.  <br/> |
   
\*-MFA umfasst Windows-Desktop, Mac, Ios, Android-Geräte und Windows phones; CBA umfasst Windows-Desktop-, IOS-und Android-Geräte; CA/MAM mit InTune, einschließlich Android-und IOS-Geräten. 
  
> [!IMPORTANT]
> Es ist sehr wichtig zu beachten, dass Benutzer möglicherweise **mehrere Eingabeaufforderungen** in einigen Fällen sehen, insbesondere dort, wo der MA-Status nicht für alle Serverressourcen identisch ist, die Clients möglicherweise benötigen, und wie dies bei allen Versionen der gemischten Topologien der Fall ist.

> [!IMPORTANT]
> Beachten Sie auch, dass in einigen Fällen (Mixed 1, 3 und 5 speziell) ein [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) -Registrierungsschlüssel für die ordnungsgemäße Konfiguration für Windows-Desktop Clients festgelegt werden muss.
  

