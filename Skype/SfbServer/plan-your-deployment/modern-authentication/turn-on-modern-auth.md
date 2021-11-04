---
title: Planen der internen und externen Deaktivierung von Legacyauthentifizierungsmethoden für Ihr Netzwerk
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In diesem Artikel werden Cmdlets beschrieben, mit denen Administratoren mehr Kontrolle über Authentifizierungsmethoden erhalten, die innerhalb und außerhalb eines Unternehmens verwendet werden. Administratoren können Authentifizierungsmethoden intern oder extern in ihrem Netzwerk aktivieren oder deaktivieren.
ms.openlocfilehash: 65ec31dcd4a320b42da746eece41009f70e886af
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777955"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen, legacy-Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren.

> [!NOTE]
> Wenn Sie diesen Artikel lesen möchten, sollten Sie bereits über unterstützte Topologien für moderne Authentifizierung, ADAL und die Konfiguration der modernen Authentifizierung informiert sein. Falls dies nicht der Fall ist, finden Sie hier die Artikel, die Sie für den Einstieg benötigen: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
Moderne Authentifizierung ermöglicht nicht nur sicherere Authentifizierungsmethoden, z. B. Two-Factor Authentifizierung oder zertifikatbasierte Authentifizierung, sie kann die Autorisierung Ihres Benutzers ausführen, ohne dass auch ein Benutzername oder Kennwort erforderlich ist. Es ist ziemlich praktisch.

Dieser Artikel hilft Ihnen beim Schließen von Löchern, die für Denial-of-Service (DOS)-Angriffe auf Skype for Business Server ausgenutzt wurden, indem sie ältere Methoden für die Authentifizierung deaktivieren, extern, intern oder beides, in Ihrem Netzwerk. Eine gute Methode zum Stoppen von DOS-Angriffen wäre beispielsweise das Deaktivieren Windows integrierten Authentifizierung (einschließlich NTLM und Kerberos). Das externe Deaktivieren von NTLM und die Verwendung der zertifikatbasierten Authentifizierung trägt zum Schutz von Kennwörtern vor Gefährdung bei. Dies liegt daran, dass NTLM Kennwortanmeldeinformationen verwendet, um Benutzer zu authentifizieren, die zertifikatbasierte Authentifizierung – durch moderne Authentifizierung aktiviert – jedoch nicht. Dies bedeutet, dass eine ideale Option zum Reduzieren von DOS-Angriffen darin besteht, NTLM extern zu blockieren und stattdessen nur die zertifikatbasierte Authentifizierung zu verwenden.

Gut, lassen Sie uns loslegen.

## <a name="what-would-you-be-changing"></a>Was würden Sie ändern? 

Diese Cmdlets funktionieren sowohl für SIP- als auch für Webdienste-Zugriffspunkte. Obwohl diese beiden Kanäle unterschiedliche Zugriffsmethoden verwenden, wobei die Bandbreite von NTLM und Kerberos bis anonymer Zugriff ausgeführt wird, wurden alle von Skype for Business verwendeten Standardmethoden berücksichtigt.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Abrufen der Cmdlets "Get- und Set-CsAuthConfig"

Diese Cmdlets werden erst nach dem kumulativen Update vom Juli 2018 (6.0.9319.534) für Microsoft Skype for Business Server 2015 installiert, und dann haben Sie eine Vielzahl von Topologien, die für Ihren Skype for Business Server eingeführt werden können.

## <a name="topologies"></a>Topologien

Es ist wichtig zu beachten, dass dies die unterstützten Topologien sind, die an diesem Szenario beteiligt sind! Wenn Sie zum Support gehen müssen, um Hilfe beim Blockieren einer Methode zu erhalten, benötigen Sie beispielsweise eine Konfiguration zwischen den folgenden Typen. 

> [!IMPORTANT]
> In der Tabelle und beschreibungen unten wird *die moderne Authentifizierung* als __MA__ abgekürzt, und Windows *integrierte Authentifizierung* wird als __Win__ abgekürzt. Zur Erinnerung besteht Windows integrierte Authentifizierung aus zwei Methoden: NTLM- und Kerberos-Authentifizierung. Sie müssen dies wissen, um die Tabelle richtig lesen zu können!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Typ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  MA       | Gewinnen        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Typ 5__   |  MA + Win       | Gewinnen        | BlockModernAuthInternally         |

__Typ 1 Beschreibung:__ Dies ist das Standardszenario, wenn MA __für__ Skype for Business Server aktiviert ist. Mit anderen Worten, dies ist der *Ausgangspunkt,* wenn MA konfiguriert ist.

__Typ 2 Beschreibung:__ Diese Topologie blockiert NTLM *extern,* lässt jedoch zu, dass NTLM oder Kerberos (für Clients, die ADAL nicht unterstützen) *intern* funktionieren. Wenn Ihre Clients ADAL unterstützen, verwenden sie MA intern.

__Typ 3 Beschreibung:__ Diese Topologie erfordert MA für alle Benutzer. Alle Ihre ADAL-fähigen Clients funktionieren in dieser Topologie, und Kennwörter werden nicht verwendet, wenn Sie beispielsweise die Verwendung von Kennwörtern mit zertifikatbasierter Authentifizierung deaktivieren.

__Typ 4 Beschreibung:__ Diese Topologie blockiert NTLM *extern* und MA intern. Es ermöglicht *allen Clients* die *interne* Verwendung von Legacyauthentifizierungsmethoden (sogar ADAL-fähige Clients).

__Typ 5 Beschreibung:__ *Extern* verwenden Ihre modernen ADAL-Clients MA, und alle Clients, die ADAL nicht unterstützen, verwenden legacy-Authentifizierungsmethoden. *Intern* verwenden *jedoch alle Clients* die Legacyauthentifizierung (einschließlich aller ADAL-fähigen Clients).

Es ist ziemlich einfach, das Ziel des Schutzes Ihrer Kennwörter in den verfügbaren Optionen nachzuverfolgen. Denken Sie daran, dass die ideale Situation darin besteht, MA extern zu verwenden (z. B. durch Konfigurieren der zertifikatbasierten Authentifizierung), um DOS-Angriffe zu vermeiden. Wenn Sie es intern für Ihre modernen Clients nutzen, werden Sie auch Ihr Netzwerk hinsichtlich Skype for Business Server DOS-Angriffen zukunftssicher machen.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für die Verwendung von Set-CsAuthConfig auf globaler Ebene

Das `Set-CsAuthConfig` Cmdlet wirkt sich auf die Registrierungsstelle und die Webdienstrollen aus.

Dieses Cmdlet sollte auf der globalen Ebene ihres Skype for Business Servers ausgeführt werden. Sie *kann* auf Poolebene ausgeführt werden, dies wird jedoch *nicht empfohlen,* da die Installation dadurch komplexer wird. Wenn Sie diese Befehle auf Poolebene ausführen, werden die Einstellungen nur für die Registrierungsstellenrolle festgelegt, wenn in Ihrem Pool nicht alle Rollen enthalten sind (z. B. keine Webdienste). In diesem Fall führen Webdienste Einstellungen auf globaler Ebene aus, was verwirrendes Verhalten sein kann (insbesondere, wenn dies unbeabsichtigt erfolgt).

Wenn ein Client die Registrierungsstelleneinstellungen aus einem Pool und die Webdiensteinstellungen aus einem anderen Pool verwendet und sich die Authentifizierungseinstellungen in einem inkonsistenten Zustand befinden, können sich Die Clients möglicherweise nicht anmelden.

Wenn nur eine Rolle für einen Pool vorhanden ist: 
* Set- legt nur die Einstellungen fest, die der vorhandenen Rolle entsprechen. Es wird keine besondere Warnung ausgegeben, da einige Einstellungen *nicht* festgelegt wurden. 
* Get- gibt die Einstellung zurück, die der vorhandenen Rolle entspricht, und die globalen Einstellungen für die Rolle, die nicht vorhanden ist.
* Wenn keine rolle für einen Pool vorhanden ist, wird sowohl "Set- " als auch "Get-" eine Fehlermeldung zurückgegeben.
* Wenn beide Rollen für einen Pool vorhanden sind, richtlinien jedoch nicht auf Poolebene definiert sind, gibt Get- eine Fehlermeldung zurück.

Es kann ratsam sein, eine Get- für diese Werte durchzuführen und den Startzustand zu screenshoten oder zu notieren, bevor Sie Änderungen vornehmen. Sie können auch erwägen, ein Änderungsprotokoll in einem OneNote zu speichern.

> [!NOTE]
> 
> Hinweis: Nach dem Konfigurieren von CsAuthConfig müssen Sie Enable-CsComputer auf jedem Computer ausführen, damit die Einstellungen wirksam werden.

> [!IMPORTANT]
> Wenn Sie Lync Web Access (LWA) verwenden und den formularbasierten Zugriff (Forms-based Access, FBA) für den externen Zugriff verwenden müssen, konfigurieren Sie LWA neu, damit Clients mit anonymem Zugriff darauf zugreifen können, um diese Szenarien zu unterstützen. Ebenso wird FBA bei Verwendung der Einwahl-Pin nur für externe Benutzer blockiert. Wenn sie ihre Pin ändern müssen, müssen sie sich intern bei ihrem Unternehmen anmelden.

> [!NOTE]
> 
> Wenn Sie den Parameter BlockWindowsAuthExternally verwenden, um NTLM extern zu blockieren, beachten Sie, dass dies auch NTLM intern für den SIP-Kanal blockiert. Skype for Business- und Lync-Clients, die neuer als 2010 sind, können sich jedoch weiterhin anmelden, da sie NTLM über HTTP intern für die Anmeldung verwenden und dann ein Zertifikat abrufen, um sich über SIP anzumelden. Clients, die älter als 2010 sind, können sich in diesem Fall jedoch nicht intern anmelden, und Sie sollten ein Upgrade dieser Anwendungen in Betracht ziehen, damit Ihre Benutzer die sichere Funktionalität fortsetzen können.

> [!IMPORTANT] 
> Einige der Skype for Business-Webanwendungen unterstützen ma nicht. Wenn Sie also das Szenario "BlockWindowsAuthExternallyAndInternally" verwenden, können Sie nicht auf diese Anwendungen zugreifen. Anwendungen ohne MA-Unterstützung sind Web scheduler, Dial-In Page, Skype for Business Control Panel (CSCP) und Response Group Einstellungen Page. 

## <a name="links"></a>Links 
- Weitere PowerShell-Informationen:
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Weitere Informationen zur Verwendung der Befehle oder auf dem CU, die zum Installieren der Befehle erforderlich sind:
    - [Briefing für Cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (Allgemein)
    - The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


