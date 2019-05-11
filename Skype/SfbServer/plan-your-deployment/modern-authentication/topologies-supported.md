---
title: Mit moderner Authentifizierung unterstützte Skype for Business-Topologien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: In diesem Artikel erfahren Sie, welche Onlinetopologien und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden und welche Sicherheitsmerkmale die Topologien jeweils aufweisen.
ms.openlocfilehash: ca7c89ce8f7f7681463bbdc87518f42130bf310e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929055"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Skype for Business topologies supported with Modern Authentication
 
In diesem Artikel erfahren Sie, welche Onlinetopologien und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden und welche Sicherheitsmerkmale die Topologien jeweils aufweisen.
  
## <a name="modern-authentication-in-skype-for-business"></a>Moderne Authentifizierung in Skype for Business

Skype for Business kann die Sicherheitsvorteile der modernen Authentifizierung nutzen. Aufgrund der engen Zusammenarbeit zwischen Skype for Business und Exchange wird das Anmeldeverhalten für Benutzer von Skype for Business-Clients auch durch den Status der modernen Authentifizierung (MA) in Exchange beeinflusst. Dies gilt auch, wenn Sie eine hybride Skype for Business-Topologie mit geteilter Domäne verwenden. Es gibt also viele Variablen, aber das Ziel ist hier eine leicht zu visualisierende Liste der unterstützten Topologien.
  
Welche Topologien werden für moderne Authentifizierung unterstützt, wenn Skype for Business, Skype for Business Online, Exchange Server und Exchange Online genutzt werden?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Unterstützte MA-Topologien in Skype for Business

An den von MA verwendeten Skype for Business-Topologien sind potenziell zwei Serveranwendungen und zwei Office 365-Workloads beteiligt.
  
- Skype für Business Server (CU 5) lokal
    
- Skype for Business Online (SFBO)
    
- Exchange Server (lokal)
    
- Exchange Server Online (EXO)
    
Ein weiterer wichtiger Aspekt von MA ist, dass Sie wissen müssen, wo die Authentifizierung (authN) und die Autorisierung (authZ) der Benutzer stattfinden soll. Die folgenden zwei Optionen stehen zur Verfügung:
  
- Azure AD, online in Microsoft Cloud
    
- Active Directory-Verbundserver (Active Directory Federation Server, AD FS) (lokal)
    
Damit sie etwas wie folgt, mit EXO und SFBO in der Cloud mit Azure AD aussieht und Exchange Server (EXCH) und Skype für Business Server (SFB) auf Vorz
  
![Ein Beispiel für alle Anwendungen (Exchange und Skype for Business) und Arbeitsauslastungen (EXO und SFBO) sowie für beide Autorisierungsserver (ADFS und evoSTS), die beim Aktivieren von MA beteiligt sein können.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Hier sind die unterstützten Topologien. Für die Grafiken gilt die folgende Legende:
  
- Wenn das Symbol ist abgeblendet oder Haus, wird es im Szenario nicht verwendet.
    
- EXO: Exchange Online
    
- SFBO: Skype for Business Online
    
- EXCH: Exchange (lokal)
    
- SFB: Skype for Business (lokal)
    
- Autorisierende Server werden durch Dreiecke dargestellt. So ist zum Beispiel Azure AD ein Dreieck mit einer Wolke dahinter.
    
- Pfeile zeigen auf den autorisierenden Server, der verwendet wird, wenn Clients die angegebene Serverressource zu erreichen versuchen.
    
Betrachten wir zunächst MA mit Skype for Business in rein lokalen Topologien und reinen Cloudtopologien.
  
> [!IMPORTANT]
> Sind Sie bereit, moderne Authentifizierung in Skype for Business Online einzurichten? Die Schritte zum Aktivieren dieser Funktion die richtige Wahl ist [hier](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Nur Cloud  <br/> |![Unterstützung für SFB mit MA-Topologie, nur Cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Verwaltung der Benutzer/Speicherort der Postfächer: online   <br/> |MA ist für EXO und SFBO aktiviert.  <br/> Daher ist Azure AD der Autorisierungsserver.  <br/> |Mehrstufige Authentifizierung (mehrstufiger Authentifizierung das), Client-zertifikatbasierte Authentifizierung (CLIENTZERTIFIKATS-) bedingten Zugriff (CA) / Mobile Application Management (MAM) mit Intune. \*  <br/> |
|Nur lokal  <br/> |![Unterstützung für SFB mit MA-Topology, nur lokal.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Verwaltung der Benutzer/Speicherort der Postfächer: lokal  <br/> |MA ist für SFB (lokal) aktiviert.  <br/> Daher ist AD FS der Autorisierungsserver.  <br/> Details zur Konfiguration finden Sie unter [in diesem Artikel.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA (Nur Windows-Desktop – mobile Clients werden nicht unterstützt.) Keine Exchange-Integrationsfunktionen.  <br/> |
   
> [!IMPORTANT]
> Der MA-Status sollte in Skype for Business und Exchange (und deren Onlinependants) gleich sein, um die Anzahl der Eingabeaufforderungen zu verringern. 
  
Bei gemischten Topologien sind Kombinationen von SFB-Hybriden mit geteilter Domäne beteiligt. Diese gemischten Topologien werden zurzeit unterstützt:
  
|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Gemischt 1  <br/> |![Unterstützung für SFB mit MA-Topologie, Gemischt 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXO und SFB  <br/> |MA ist für SFB nicht aktiviert, in dieser Topologie sind keine MA-Funktionen für SFB verfügbar.  <br/> |Keine MA-Funktionen für SFB  <br/> |
|Gemischt 2  <br/> |![Unterstützung für MA mit gemischter S4B-Topologie 2, SFBO plus MA in lokaler Zusammenarbeit mit EXCH.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXCH und SFBO  <br/> |MA ist nur für SFBO aktiviert. Der autorisierungsserver ist Azure AD für Benutzer in SFBO, aber AD für EXCH lokal verwaltet.  <br/> |Mehrstufiger Authentifizierung das, CLIENTZERTIFIKATS-Zertifizierungsstelle/MAM mit Intune.\*  <br/> |
|Gemischt 3  <br/> |![Unterstützung für MA mit SFB, EXO mit aktiviertem MA plus lokalem EXCH und SFB.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXO + SFB oder EXCH + SFB  <br/> |In dieser Topologie sind keine MA-Funktionen für SFB verfügbar.  <br/> |Keine MA-Funktionen für SFB  <br/> |
|Gemischt 4  <br/> |![Unterstützung für MA mit SFB, SFBO mit aktiviertem MA plus lokalem EXCH und SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXCH + SFBO oder EXCH + SFB  <br/> |MA ist für SFBO, daher autorisierungsserver Azure AD für Benutzer in SFBO verwaltet wird. Klicken Sie auf Prem-Benutzer in SFB und EXO verwenden AD.  <br/> |Mehrstufiger Authentifizierung das, CLIENTZERTIFIKATS-Zertifizierungsstelle/MAM mit Intune für online-Benutzern.\*  <br/> |
|Gemischt 5  <br/> |![Unterstützung für MA in SFB, EXO mit MA und SFBO mit MA sowie lokalem EXCH und SFB.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXO und SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |Verwaltungs-Agent ist auf in EXO und SFBO, daher autorisierungsserver Azure AD ist für Benutzer in SFBO verwaltet. Klicken Sie auf Prem-Benutzer in EXCH und SFB verwenden AD.  <br/> |Mehrstufiger Authentifizierung das, CLIENTZERTIFIKATS-Zertifizierungsstelle/MAM mit Intune für online-Benutzern.\*  <br/> |
|Gemischte 6  <br/> |![In der Topologie „Gemischt 6“ ist moderne Authentifizierung an allen vier möglichen Standorten aktiviert – die ideale Situation im Hinblick auf moderne Authentifizierung.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Verwaltung der Benutzer/Speicherort der Postfächer: EXO und SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |Verwaltungs-Agent ist auf überall, daher wird des autorisierungsservers Azure AD für alle Benutzer. (online und lokale)  <br/>  Bitte finden Sie unter [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) für Bereitstellungsschritte. <br/> |Mehrstufiger Authentifizierung das, CLIENTZERTIFIKATS- und Zertifizierungsstelle/MAM (über Intune) für alle Benutzer.  <br/> |
   
\*-Mehrstufiger Authentifizierung das umfasst Windows-Desktop, MAC, iOS, Android-Geräte und Windows-Telefonen. CBA umfasst Windows-Desktop, iOS und Android-Geräte. Zertifizierungsstelle/MAM mit Intune, umfasst Android und iOS-Geräte. 
  
> [!IMPORTANT]
> Sehr wichtig ist, dass die Benutzer möglicherweise in manchen Fällen **mehrere Eingabeaufforderungen** sehen, vor allem, wenn der MA-Status nicht auf allen von den Clients benötigten und angeforderten Serverressourcen gleich ist. Dies gilt für alle Versionen der gemischten Topologien. 

> [!IMPORTANT]
> Beachten Sie, dass auch in einigen Fällen (gemischt insbesondere 1, 3 und 5) für die ordnungsgemäße Konfiguration für Windows-Desktop-Clients muss ein [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) Registrierungsschlüssel festgelegt werden.
  

