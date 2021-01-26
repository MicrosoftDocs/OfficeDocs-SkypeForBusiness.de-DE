---
title: Planen des internen und externen Deaktivierens von Legacyauthentifizierungsmethoden für Ihr Netzwerk
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
ms.assetid: ''
description: In diesem Artikel werden Cmdlets beschrieben, die Administratoren mehr Kontrolle über die innerhalb und außerhalb eines Unternehmens verwendeten Authentifizierungsmethoden bieten. Administratoren können Authentifizierungsmethoden intern oder extern in ihrem Netzwerk aktivieren oder deaktivieren.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810025"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen der internen und externen Deschaltierung von Legacyauthentifizierungsmethoden für Ihr Netzwerk.

> [!NOTE]
> Wenn Sie diesen Artikel lesen möchten, sollten Sie bereits über unterstützte Topologien für die moderne Authentifizierung, ADAL und die Konfiguration der modernen Authentifizierung wissen. Falls Sie dies nicht möchten, finden Sie hier die Artikel, die Sie zunächst lesen müssen: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Die moderne Authentifizierung ermöglicht nicht nur sicherere Authentifizierungsmethoden, z. B. Two-Factor Authentifizierung oder zertifikatbasierte Authentifizierung, sondern kann auch die Autorisierung Ihres Benutzers durchführen, ohne dass ein Benutzername oder ein Kennwort erforderlich ist. Es ist ziemlich praktisch.

Dieser Artikel hilft Ihnen, Lücke zu schließen, die für Denial of Service (DOS)-Angriffe auf Skype for Business Server ausgenutzt wurden, indem Sie ältere Methoden für die Authentifizierung deaktivieren, die extern, intern oder beides für Ihr Netzwerk verwendet werden. Eine gute Methode zum Stoppen von DOS-Angriffen wäre beispielsweise das Deaktivieren der integrierten Windows-Authentifizierung (einschließlich NTLM und Kerberos). Das externe Deaktivieren von NTLM und die Verwendung der zertifikatbasierten Authentifizierung trägt zum Schutz von Kennwörtern vor der Gefährdung bei. Dies liegt daran, dass NTLM Kennwortanmeldeinformationen verwendet, um Benutzer zu authentifizieren, die zertifikatbasierte Authentifizierung – aktiviert durch moderne Authentifizierung – jedoch nicht. Dies bedeutet, dass eine ideale Option zur Reduzierung von DOS-Angriffen ist, NTLM extern zu blockieren und stattdessen nur die zertifikatbasierte Authentifizierung zu verwenden.

Alles in Ordnung, lassen Sie uns beginnen.

## <a name="what-would-you-be-changing"></a>Was würden Sie ändern? 

Diese Cmdlets funktionieren sowohl für SIP- als auch für Webdienste-Zugriffspunkte. Obwohl diese beiden Kanäle unterschiedliche Zugriffsmethoden verwenden und die Gamut von NTLM und Kerberos bis zum anonymen Zugriff ausführen, wurden alle von Skype for Business verwendeten Standardmethoden berücksichtigt.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>So erhalten Sie die Cmdlets "Get- and Set-CsAuthConfig"

Diese Cmdlets werden erst nach dem kumulativen Update vom Juli 2018 (6.0.9319.534) für Microsoft Skype for Business Server 2015 installiert. Anschließend haben Sie eine Vielzahl von Topologien, die für Ihren Skype for Business-Server eingerichtet werden können.

## <a name="topologies"></a>Topologien

Beachten Sie, dass es sich dabei um die unterstützten Topologien handelt, die in diesem Szenario verwendet werden. Wenn Sie beispielsweise zum Support wechseln müssen, um Hilfe beim Blockieren einer Methode zu erhalten, benötigen Sie eine Konfiguration unter den folgenden Typen. 

> [!IMPORTANT]
> In der folgenden Tabelle und Beschreibungen wird die moderne *Authentifizierung* als __MA__ abgekürzt, und die integrierte *Windows-Authentifizierung* wird als Win __abgekürzt.__ Zur Erinnerung: Die integrierte Windows-Authentifizierung besteht aus zwei Methoden: NTLM- und Kerberos-Authentifizierung. Sie müssen dies wissen, um die Tabelle richtig lesen zu können!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Typ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Typ 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Typ 1 Beschreibung:__ Dies ist das Standardszenario, wenn MA __für__ Skype for Business Server aktiviert ist. Das heißt, dies ist der *Ausgangspunkt, wenn* MA konfiguriert ist.

__Typ 2 Beschreibung:__ Diese Topologie blockiert NTLM *extern,* ermöglicht jedoch die interne Verwendung von NTLM oder Kerberos (für Clients, die ADAL nicht *unterstützen).* Wenn Ihre Clients ADAL unterstützen, verwenden sie MA intern.

__Typ 3 Beschreibung:__ Für diese Topologie ist MA für alle Benutzer erforderlich. Alle ADAL-fähigen Clients funktionieren in dieser Topologie, und Kennwörter werden nicht verwendet, wenn Sie beispielsweise die Verwendung von Kennwörtern mit zertifikatbasierter Authentifizierung deaktivieren.

__Typ 4 Beschreibung:__ Diese Topologie blockiert NTLM *extern und* MA intern. Es ermöglicht *allen Clients die* interne Verwendung von Legacyauthentifizierungsmethoden (sogar ADAL-fähige Clients). 

__Typ 5 Beschreibung:__ *Extern* verwenden Ihre modernen ADAL-Clients MA, und alle Clients, die ADAL nicht unterstützen, verwenden Legacyauthentifizierungsmethoden. Intern verwenden *jedoch alle* *Clients* legacybasierte Authentifizierung (einschließlich aller ADAL-fähigen Clients).

Es ist ziemlich einfach, den Überblick über das Ziel zu verlieren, Ihre Kennwörter in den verfügbaren Optionen zu schützen. Denken Sie daran, dass die ideale Situation die externe Verwendung von MA ist (z. B. durch Konfigurieren der zertifikatbasierten Authentifizierung), um DOS-Angriffe zu vermeiden. Wenn Sie es intern für Ihre modernen Clients nutzen, sind Sie auch in Bezug auf Skype for Business Server-DOS-Angriffe zukunftssicher für Ihr Netzwerk.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für die Verwendung Set-CsAuthConfig auf globaler Ebene

Das `Set-CsAuthConfig` Cmdlet wirkt sich auf die Konfiguration sowohl auf die Registrierungsrolle als auch auf die Webdienstrollen aus.

Dieses Cmdlet sollte auf der globalen Ebene Ihres Skype for Business-Servers ausgeführt werden. Sie *kann* auf Poolebene ausgeführt werden, wird jedoch *nicht* empfohlen, da die Installation dadurch komplexer wird. Durch Ausführen dieser Befehle auf Poolebene werden die Einstellungen nur für die Registrierungsrolle festgelegt, wenn nicht alle Rollen in Ihrem Pool enthalten sind (z. B. keine Webdienste). In diesem Fall werden Webdienste mit Einstellungen auf globaler Ebene weiter verwendet, was verwirrend sein kann (insbesondere dann, wenn dies unbeabsichtigt erfolgt).

Wenn ein Client die Registrierungseinstellungen aus einem Pool und die Webdiensteeinstellungen eines anderen Pools verwendet und sich die Authentifizierungseinstellungen in einem inkonsistenten Zustand befinden, können sich Die Clients möglicherweise nicht anmelden.

Wenn nur eine Rolle für einen Pool vorhanden ist: 
* Set- setzt nur die Einstellungen, die der vorhandenen Rolle entsprechen. Es wird keine besondere Warnung angezeigt, da einige Einstellungen *nicht festgelegt* wurden. 
* Get- gibt die Einstellung zurück, die der vorhandenen Rolle und den globalen Einstellungen für die rolle entspricht, die nicht vorhanden ist.
* Wenn keine rolle für einen Pool vorhanden ist, wird sowohl "Set-" als auch "Get-" eine Fehlermeldung zurückgegeben.
* Wenn beide Rollen für einen Pool vorhanden sind, richtlinien jedoch nicht auf Poolebene definiert sind, gibt Get- eine Fehlermeldung zurück.

Es kann am einfachsten sein, für diese Werte ein Get- zu erstellen und den Startzustand zu screenshoten oder zu notieren, bevor Sie Änderungen vornehmen. Sie können auch erwägen, ein Protokoll der Änderungen in oneNote zu speichern.

> [!NOTE]
> 
> Hinweis: Nach dem Konfigurieren von "CsAuthConfig" müssen Sie Enable-CsComputer auf jedem Computer ausführen, damit die Einstellungen wirksam werden.

> [!IMPORTANT]
> Wenn Sie Lync Web Access (LWA) verwenden und formularbasierten Zugriff (FBA) für den externen Zugriff verwenden müssen, konfigurieren Sie LWA neu, damit Clients mit anonymen Zugriff darauf zugreifen können, um diese Szenarien zu unterstützen. Ebenso wird FBA bei Verwendung von Einwahl-Pin nur für externe Benutzer blockiert. Wenn sie ihre Pin ändern müssen, müssen sie sich intern bei ihrem Unternehmen anmelden.

> [!NOTE]
> 
> Wenn Sie den Parameter "BlockWindowsAuthExternally" verwenden, um NTLM extern zu blockieren, ist zu beachten, dass dadurch auch NTLM intern für den SIP-Kanal blockiert wird. Skype for Business- und Lync-Clients, die neuer als 2010 sind, können sich jedoch weiterhin anmelden, da sie NTLM über HTTP für die Anmeldung intern verwenden und dann ein Zertifikat für die Anmeldung über SIP abrufen. Clients, die älter als 2010 sind, können sich in diesem Fall jedoch nicht intern anmelden, und Sie sollten ein Upgrade dieser Anwendungen in Betracht ziehen, damit Ihre Benutzer die sichere Funktionalität fortsetzen können.

> [!IMPORTANT] 
> Einige der Skype for Business-Webanwendungen unterstützen MA nicht. Wenn Sie also das Szenario "BlockWindowsAuthExternallyAndInternally" verwenden, können Sie nicht auf diese Anwendungen zugreifen. Anwendungen ohne MA-Unterstützung sind Web scheduler, Dial-In Page, Skype for Business Control Panel (CSCP) und Response Group Settings Page. 

## <a name="links"></a>Links 
- Weitere Informationen zu PowerShell finden Sie unter:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- For more direction on how to use the commands or on the CU needed to install them:
    - [Cmdlets briefing](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (Allgemein)
    - The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
