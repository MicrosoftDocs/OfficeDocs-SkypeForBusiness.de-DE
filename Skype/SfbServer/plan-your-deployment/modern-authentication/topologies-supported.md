---
title: Unterstützte Skype for Business-Topologien mit moderner Authentifizierung
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
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Dieser Artikel listet auf, welche Online- und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für jede Topologie gelten.
ms.openlocfilehash: 759ee11a4cd6828d65b45a713f50bb8b32856a4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116063"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Unterstützte Skype for Business-Topologien mit moderner Authentifizierung

Dieser Artikel listet auf, welche Online- und lokalen Topologien mit moderner Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für jede Topologie gelten.

## <a name="modern-authentication-in-skype-for-business"></a>Moderne Authentifizierung in Skype for Business

Skype for Business kann die Sicherheitsvorteile der modernen Authentifizierung nutzen. Da Skype for Business eng mit Exchange zusammenarbeiten kann, wird das Anmeldeverhalten von Skype for Business-Clientbenutzern auch vom Ma-Status von Exchange beeinflusst. Dies gilt auch, wenn Sie über eine Skype for Business-Hybriddomäne mit geteilter Domäne verfügen. Dies sind viele verschiebende Teile, aber das Ziel hier ist eine leicht zu visualisierende Liste der unterstützten Topologien.

Welche Topologien werden in Skype for Business, Skype for Business online, Exchange Server und Exchange online unterstützt?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Unterstützte MA-Topologien in Skype for Business

Es gibt potenziell zwei Serveranwendungen und zwei Microsoft 365- oder Office 365-Workloads, die an Skype for Business-Topologien beteiligt sind, die von MA verwendet werden.

- Skype for Business Server (CU 5) lokal

- Skype for Business online (SFBO)

- Exchange-Server lokal

- Exchange-Server online (EXO)

Ein weiterer wichtiger Teil von MA ist zu wissen, wo die Authentifizierung (authN) und autorisierung (authZ) von Benutzern stattfinden. Die beiden Optionen sind:

- Azure AD, online in der Microsoft Cloud

- Active Directory Federation Server (ADFS) lokal

Es sieht also ein wenig so aus, mit EXO und SFBO in der Cloud mit Azure AD und Exchange Server (EXCH) und Skype for Business Server (SFB) on-prem.

![Ein Beispiel für alle Anwendungen (Exchange und Skype for Business) und Workloads (EXO und SFBO) sowie beide Autorisierungsserver (ADFS und evoSTS), die beim Aktivieren von MA beteiligt sein können.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Hier sind die unterstützten Topologien. Beachten Sie den Schlüssel für die Grafiken:

- Wenn das Symbol abgeblendet oder grau ist, wird es im Szenario nicht verwendet.

- EXO ist Exchange Online.

- SFBO ist Skype for Business Online.

- EXCH ist lokal in Exchange.

- SFB ist lokal Skype for Business.

- Autorisierungsserver werden durch Dreiecke dargestellt, z. B. ist Azure AD ein Dreieck mit einer Cloud dahinter.

- Pfeile zeigen auf den Autorisierungsserver, der verwendet wird, wenn Clients versuchen, die angegebene Serverressource zu erreichen.

Als Erstes werden wir ma mit Skype for Business sowohl in lokalen topologien als auch in Cloudtopologien abdecken.

> [!IMPORTANT]
> Sind Sie bereit, die moderne Authentifizierung in Skype for Business Online einrichten? Die Schritte zum Aktivieren dieses Features finden Sie [hier](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Nur für die Cloud  <br/> |![Unterstützte SFB mit MA-Topologie, nur Cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Gespeicherte Benutzer/Postfächer: Online  <br/> |MA ist sowohl für EXO als auch für SFBO ein.  <br/> Daher ist der Autorisierungsserver Azure AD.  <br/> |Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), Clientzertifikatbasierte Authentifizierung (CBA), Bedingter Zugriff (CA)/Mobile Application Management (MAM) mit Intune. \*  <br/> |
|Nur on-prem  <br/> |![Unterstützte SFB mit MA-Topologie, nur lokal.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Benutzer, die sich im Homed/Mailboxes-Standort befinden: Lokal  <br/> |MA ist für SFB lokal.  <br/> Daher ist der Autorisierungsserver ADFS.  <br/> Konfigurationsdetails finden Sie in [diesem Artikel.](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (nur Windows Desktop – mobile Clients werden nicht unterstützt). Keine Exchange-Integrationsfeatures.  <br/><p> **Wir empfehlen diesen Ansatz nicht. Weitere Informationen finden Sie hier:**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> Es wird empfohlen, den Ma-Status in Skype for Business und Exchange (und ihren Online-Entsprechungen) gleich zu sein, um die Anzahl der Eingabeaufforderungen zu reduzieren.

Gemischte Topologien umfassen Kombinationen von Hybriden mit geteilter SFB-Domäne. Dies sind die derzeit unterstützten gemischten Topologien:

|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Gemischt 1  <br/> |![Unterstützte SFB mit MA-Topologie, Mixed 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Benutzer, die sich befinden: EXO und SFB  <br/> |MA ist für SFB nicht aktiviert. In dieser Topologie sind keine SFB MA-Features verfügbar.  <br/> |Keine MA-Funktionen für SFB.  <br/> |
|Gemischt 2  <br/> |![Unterstützte MA mit S4B Mixed topology 2, SFBO plus MA, die mit EXCH on-prem arbeiten.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Gespeicherte Benutzer/Postfächer: EXCH und SFBO  <br/> |MA ist nur für SFBO ein. Der Autorisierungsserver ist Azure AD für Benutzer, die in SFBO, aber AD für EXCH lokal gehostet werden.  <br/> |MFA, CBA, CA/MAM mit Intune.\*  <br/> |
|Gemischt 3  <br/> |![Unterstützte MA mit SFB, EXO mit MA on sowie EXCH und SFB lokal.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Benutzer, die sich befinden: EXO + SFB oder EXCH + SFB  <br/> |In dieser Topologie sind keine SFB MA-Funktionen verfügbar  <br/> |Keine MA-Funktionen für SFB.  <br/> |
|Gemischt 4  <br/> |![Unterstützte MA mit SFB, SFBO mit MA on sowie EXCH und SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Benutzer, die sich befinden: EXCH +SFBO oder EXCH + SFB  <br/> |MA ist für SFBO verfügbar, daher ist der Autorisierungsserver Azure AD für Benutzer, die in SFBO gehostet werden. Benutzer vor Ort in SFB und EXO verwenden AD.  <br/> |MFA, CBA, CA/MAM mit Intune nur für Onlinebenutzer.\*  <br/> |
|Gemischt 5  <br/> |![Unterstützte MA in SFB, EXO mit MA und SFBO mit MA sowie EXCH und SFB lokal.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Benutzer, die sich befinden: EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |MA ist sowohl in EXO als auch in SFBO verfügbar, daher ist der Autorisierungsserver Azure AD für Benutzer, die in SFBO gehostet werden. On-Prem-Benutzer in EXCH und SFB verwenden AD.  <br/> |MFA, CBA, CA/MAM mit Intune nur für Onlinebenutzer.\*  <br/> |
|Gemischt 6  <br/> |![In einer Mixed 6-Topologie ist die moderne Authentifizierung an allen vier geeigneten Speicherorten aktiviert – die ideale Situtation, wenn es um moderne Authentifizierung geht.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Benutzer, die sich befinden: EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |MA ist überall verfügbar, daher ist der Autorisierungsserver Azure AD für alle Benutzer. (online und lokal)  <br/>  Die [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) Bereitstellungsschritte finden Sie unter. <br/> |MFA, CBA und CA/MAM (über Intune) für alle Benutzer.  <br/> |

\* - MFA umfasst Windows Desktop, MAC, iOS, Android-Geräte und Windows Phones; CBA umfasst Windows Desktop-, iOS- und Android-Geräte; CA/MAM mit Intune, umfasst Android- und iOS-Geräte.

> [!IMPORTANT]
> Es ist sehr wichtig zu beachten, dass benutzern in einigen Fällen möglicherweise mehrere Eingabeaufforderungen angezeigt werden, insbesondere wenn der Ma-Status nicht für alle Serverressourcen identisch ist, die Clients möglicherweise benötigen und anfordern, wie **dies** bei allen Versionen der gemischten Topologien der Fall ist.

> [!IMPORTANT]
> Beachten Sie außerdem, dass in einigen Fällen (gemischt 1, 3 und 5) ein [AllowADALForNonLyncIndependentOfLync-Registrierungsschlüssel](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) für die ordnungsgemäße Konfiguration für Windows-Desktopclients festgelegt werden muss.