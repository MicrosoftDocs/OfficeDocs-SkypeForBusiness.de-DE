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
description: In diesem Artikel werden die Online- und lokalen Topologien aufgeführt, die mit der modernen Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für jede Topologie gelten.
ms.openlocfilehash: 6bc61f8517200ffc7de4b836caabdbafe547929a2a947b4acb62821941f5bdc5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352633"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Unterstützte Skype for Business-Topologien mit moderner Authentifizierung

In diesem Artikel werden die Online- und lokalen Topologien aufgeführt, die mit der modernen Authentifizierung in Skype for Business unterstützt werden, sowie Sicherheitsfeatures, die für jede Topologie gelten.

## <a name="modern-authentication-in-skype-for-business"></a>Moderne Authentifizierung in Skype for Business

Skype for Business können die Sicherheitsvorteile der modernen Authentifizierung nutzen. Da Skype for Business eng mit Exchange zusammenarbeiten, wird das Anmeldeverhalten Skype for Business Clientbenutzer auch vom MA-Status der Exchange beeinflusst. Dies gilt auch, wenn Sie über eine Skype for Business Hybridlösung mit geteilter Domäne verfügen. Dies sind viele verlagernde Teile, aber das Ziel ist hier eine einfache Liste der unterstützten Topologien.

Welche Topologien werden bei Skype for Business, Skype for Business online, Exchange Server und Exchange online mit MA unterstützt?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Unterstützte MA-Topologien in Skype for Business

Es gibt möglicherweise zwei Serveranwendungen und zwei Microsoft 365 oder Office 365 Workloads, die an Skype for Business topologien beteiligt sind, die von MA verwendet werden.

- Skype for Business Server (CU 5) lokal

- Skype for Business online (SFBO)

- Exchange lokalen Server

- Exchange Server online (EXO)

Ein weiterer wichtiger Bestandteil von MA ist zu wissen, wo die Authentifizierung (authN) und die Autorisierung (authZ) von Benutzern stattfinden wird. Die beiden Optionen sind:

- Azure AD, online in der Microsoft Cloud

- Lokale Active Directory-Verbundserver (Ad FS)

Es sieht also ein wenig wie folgt aus, mit EXO und SFBO in der Cloud mit Azure AD und Exchange Server (EXCH) und Skype for Business Server (SFB) lokal.

![Ein Beispiel für alle Anwendungen (Exchange und Skype for Business) und Workloads (EXO und SFBO) sowie die beiden Autorisierungsserver (ADFS und evoSTS), die beim Aktivieren von MA beteiligt sein können.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Hier sind die unterstützten Topologien. Beachten Sie den Schlüssel für die Grafiken:

- Wenn das Symbol abgeblendet oder grau ist, wird es in diesem Szenario nicht verwendet.

- EXO ist Exchange Online.

- SFBO ist Skype for Business Online.

- EXCH ist Exchange lokal.

- SFB ist Skype for Business lokal.

- Autorisierungsserver werden durch Dreiecke dargestellt, z. B. ist Azure AD ein Dreieck mit einer Cloud dahinter.

- Pfeile zeigen auf den Autorisierungsserver, der verwendet wird, wenn Clients versuchen, die angegebene Serverressource zu erreichen.

Zunächst befassen wir uns mit MA mit Skype for Business sowohl in lokalen als auch in reinen Cloudtopologien.

> [!IMPORTANT]
> Sind Sie bereit, die moderne Authentifizierung in Skype for Business Online einzurichten? Die Schritte zum Aktivieren dieses Features finden Sie [direkt hier.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)

|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Nur für die Cloud  <br/> |![Unterstützter SFB mit MA-Topologie, nur Cloud.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Verwalteten Benutzer/Postfächer: Online  <br/> |MA ist für EXO und SFBO aktiviert.  <br/> Daher ist der Autorisierungsserver Azure AD.  <br/> |Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA), clientzertifikatbasierte Authentifizierung (CBA), bedingter Zugriff (Ca)/Mobile Application Management (MAM) mit Intune. \*  <br/> |
|Nur lokal  <br/> |![Unterstützter SFB mit MA-Topologie, nur lokal.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Benutzer verwaltet/Postfächer: lokal  <br/> |MA ist für SFB lokal aktiviert.  <br/> Daher ist der Autorisierungsserver ADFS.  <br/> Einzelheiten zur Konfiguration finden Sie in [diesem Artikel.](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (nur Windows Desktop – mobile Clients werden nicht unterstützt). Keine Exchange Integrationsfeatures.  <br/><p> **Dieser Ansatz wird nicht empfohlen. Weitere Informationen finden Sie hier:**[https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> Es wird empfohlen, dass der MA-Status für Skype for Business und Exchange (und deren Online-Entsprechungen) identisch ist, um die Anzahl der Eingabeaufforderungen zu verringern.

Bei gemischten Topologien handelt es sich um Kombinationen von SFB-Hybriden mit geteilter Domäne. Dies sind die derzeit unterstützten gemischten Topologien:

|Topologiename  <br/> |Beispiel  <br/> |Beschreibung  <br/> |Unterstützt  <br/> |
|:-----|:-----|:-----|:-----|
|Gemischt 1  <br/> |![Unterstützter SFB mit MA-Topologie, Mixed 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Benutzer verwaltet/Postfächer: EXO und SFB  <br/> |MA ist für SFB nicht aktiviert; In dieser Topologie sind keine SFB MA-Features verfügbar.  <br/> |Keine MA-Features für SFB.  <br/> |
|Gemischt 2  <br/> |![Unterstützter MA mit gemischter S4B-Topologie 2, SFBO und MA, die mit EXCH lokal arbeiten.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Benutzer verwaltet/Postfächer: EXCH und SFBO  <br/> |MA ist nur für SFBO aktiviert. Der Autorisierungsserver ist Azure AD für Benutzer, die in SFBO verwaltet werden, ad für exch lokal.  <br/> |MFA, CBA, CA/MAM mit Intune.\*  <br/> |
|Gemischt 3  <br/> |![Unterstützter MA mit SFB, EXO mit aktivierter MA sowie exch und sfb lokal.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Benutzer verwaltet/Postfächer: EXO + SFB oder EXCH + SFB  <br/> |Keine SFB MA-Features in dieser Topologie verfügbar  <br/> |Keine MA-Features für SFB.  <br/> |
|Gemischt 4  <br/> |![Unterstützter MA mit SFB, SFBO mit aktivierter MA sowie EXCH und SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Benutzer verwaltet/Postfächer: EXCH +SFBO oder EXCH + SFB  <br/> |MA ist für SFBO aktiviert, daher ist der Autorisierungsserver Azure AD für Benutzer, die in SFBO verwaltet werden. Lokale Benutzer in SFB und EXO verwenden AD.  <br/> |MFA, CBA, CA/MAM mit Intune nur für Onlinebenutzer.\*  <br/> |
|Gemischt 5  <br/> |![Unterstützte MA in SFB, EXO mit MA und SFBO mit MA sowie exch und sfb lokal.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Benutzer verwaltet/Postfächer: EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |MA ist sowohl in EXO als auch in SFBO aktiviert, daher ist der Autorisierungsserver Azure AD für Benutzer, die in SFBO verwaltet werden. Lokale Benutzer in EXCH und SFB verwenden AD.  <br/> |MFA, CBA, CA/MAM mit Intune nur für Onlinebenutzer.\*  <br/> |
|Gemischt 6  <br/> |![In einer gemischten 6-Topologie ist die moderne Authentifizierung an allen vier Possibile-Speicherorten aktiviert – die ideale Situation, wenn es um moderne Authentifizierung geht.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Benutzer verwaltet/Postfächer: EXO + SFBO, EXO + SFB, EXCH + SFBO oder EXCH + SFB  <br/> |MA ist überall aktiviert, daher ist der Autorisierungsserver Azure AD für alle Benutzer. (online und lokal)  <br/>  Weitere Informationen finden Sie [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) in den Bereitstellungsschritten. <br/> |MFA, CBA und CA/MAM (über Intune) für alle Benutzer.  <br/> |

\*– MFA umfasst Windows Desktop-, MAC-, iOS-, Android-Geräte und Windows Telefone; CBA umfasst Windows Desktop-, iOS- und Android-Geräte; CA/MAM mit Intune, umfasst Android- und iOS-Geräte.

> [!IMPORTANT]
> Es ist sehr wichtig zu beachten, dass Benutzern in einigen Fällen **möglicherweise mehrere Eingabeaufforderungen** angezeigt werden, insbesondere wenn der MA-Status nicht für alle Serverressourcen identisch ist, die Clients möglicherweise benötigen und anfordern, wie dies bei allen Versionen der gemischten Topologien der Fall ist.

> [!IMPORTANT]
> Beachten Sie außerdem, dass in einigen Fällen (speziell mixed 1, 3 und 5) ein [AllowADALForNonLyncIndependentOfLync-Registrierungsschlüssel](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) für die ordnungsgemäße Konfiguration für Windows Desktopclients festgelegt werden muss.