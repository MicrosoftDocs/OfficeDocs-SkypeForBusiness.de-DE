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
description: In diesem Artikel werden Cmdlets beschrieben, die Administratoren mehr Kontrolle über die innerhalb und außerhalb eines Unternehmens verwendeten Authentifizierungsmethoden geben. Administratoren können Authentifizierungsmethoden intern oder extern für ihr Netzwerk aktivieren oder deaktivieren.
ms.openlocfilehash: 3d7217167f7e72c4db0ec438fb20d746cd612cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116053"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen, legacy-Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren.

> [!NOTE]
> Wenn Sie diesen Artikel lesen möchten, sollten Sie bereits über unterstützte Topologien für moderne Authentifizierung, ADAL und über die Konfiguration der modernen Authentifizierung wissen, aber falls nicht, sind hier die Artikel, die Sie beginnen müssen: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
Die moderne Authentifizierung ermöglicht nicht nur sicherere Authentifizierungsmethoden, wie z. B. Two-Factor Auth oder zertifikatbasierte Authentifizierung, sondern kann die Autorisierung Ihres Benutzers auch ohne Benutzernamen oder Kennwort durchführen. Es ist ziemlich praktisch.

Dieser Artikel hilft Ihnen dabei, Lücken zu schließen, die für Denial Of Service (DOS)-Angriffe auf Skype for Business-Server ausgenutzt wurden, indem Sie ältere Methoden für die Authentifizierung extern, intern oder beides für Ihr Netzwerk deaktivieren. Eine gute Methode zum Beenden von DOS-Angriffen wäre beispielsweise das Deaktivieren der integrierten Windows-Authentifizierung (einschließlich NTLM und Kerberos). Das externe Deaktivieren von NTLM und das Verlassen auf die zertifikatbasierte Authentifizierung trägt zum Schutz von Kennwörtern vor der Belichtung bei. Dies liegt daran, dass NTLM Kennwortanmeldeinformationen verwendet, um Benutzer zu authentifizieren, die zertifikatbasierte Authentifizierung -- aktiviert durch moderne Auth -- jedoch nicht. Das bedeutet, dass eine ideale Option zur Reduzierung von DOS-Angriffen ist, NTLM extern zu blockieren und stattdessen nur die zertifikatbasierte Authentifizierung zu verwenden.

Alles in Ordnung, los geht's.

## <a name="what-would-you-be-changing"></a>Was würden Sie ändern? 

Diese Cmdlets funktionieren sowohl für SIP- als auch für Webdienste-Zugriffspunkte. Obwohl diese beiden Kanäle unterschiedliche Zugriffsmethoden verwenden und den Gamut von NTLM und Kerberos auf anonymen Zugriff ausführen, wurden alle von Skype for Business verwendeten Standardmethoden berücksichtigt.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>So erhalten Sie die Cmdlets Get- und Set-CsAuthConfig

Diese Cmdlets werden erst nach dem kumulativen Update vom Juli 2018 (6.0.9319.534) für Microsoft Skype for Business Server 2015 installiert, und Dann haben Sie eine Vielzahl von Topologien, die für Ihren Skype for Business-Server ausgeführt werden können.

## <a name="topologies"></a>Topologien

Beachten Sie, dass dies die unterstützten Topologien sind, die in diesem Szenario beteiligt sind. Wenn Sie beispielsweise zu Support wechseln müssen, um Hilfe beim Blockieren einer Methode zu erhalten, benötigen Sie eine Konfiguration zwischen den folgenden Typen. 

> [!IMPORTANT]
> In der folgenden Tabelle und beschreibungen wird *die* moderne Authentifizierung als __MA__ abgekürzt, und *die integrierte Windows-Authentifizierung* wird als Win __abgekürzt.__ Zur Erinnerung: Die integrierte Windows-Authentifizierung besteht aus zwei Methoden: NTLM- und Kerberos-Authentifizierung. Sie müssen dies wissen, um die Tabelle richtig lesen zu können!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Typ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Typ 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Typ 1 Beschreibung:__ Dies ist das Standardszenario, wenn MA __für__ Skype for Business Server aktiviert ist. Mit anderen Worten, dies ist der *Ausgangspunkt,* wenn MA konfiguriert ist.

__Typ 2 Beschreibung:__ Diese Topologie blockiert NTLM *extern,* ermöglicht jedoch, dass NTLM oder Kerberos (für Clients, die ADAL nicht unterstützen) intern *funktionieren.* Wenn Ihre Clients ADAL unterstützen, verwenden sie MA intern.

__Typ 3 Beschreibung:__ Für diese Topologie ist MA für alle Benutzer erforderlich. Alle ADAL-fähigen Clients funktionieren in dieser Topologie, und Kennwörter werden nicht verwendet, wenn Sie beispielsweise die Verwendung von Kennwörtern mit zertifikatbasierter Authentifizierung deaktivieren.

__Typ 4 Beschreibung:__ Diese Topologie blockiert NTLM *extern und* MA intern. Es ermöglicht *allen Clients* die interne Verwendung von Legacyauthentifizierungsmethoden *(sogar* ADAL-fähige Clients).

__Typ 5 Beschreibung:__ *Extern* verwenden Ihre modernen ADAL-Clients MA, und alle Clients, die ADAL nicht unterstützen, verwenden Legacyauthentifizierungsmethoden. Intern verwenden *jedoch alle* *Clients* die Legacyauthentifizierung (einschließlich aller ADAL-fähigen Clients).

Es ist ziemlich einfach, den Überblick über das Ziel zu verlieren, Ihre Kennwörter in den verfügbaren Optionen zu schützen. Denken Sie daran, dass es ideal ist, MA extern zu verwenden (z. B. durch Konfigurieren der zertifikatbasierten Authentifizierung), um DOS-Angriffe zu vermeiden. Wenn Sie es intern für Ihre modernen Clients nutzen, werden Sie ihr Netzwerk auch hinsichtlich skype for Business Server-DOS-Angriffen zukunftssicher machen.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für die Verwendung Set-CsAuthConfig auf globaler Ebene

Das `Set-CsAuthConfig` Cmdlet wirkt sich auf die Konfiguration auf die Rollen Registrierung und Webdienste aus.

Dieses Cmdlet soll auf globaler Ebene Ihres Skype for Business-Servers ausgeführt werden. Sie *kann* auf Poolebene ausgeführt werden, dies wird *jedoch nicht* empfohlen, da die Installation dadurch komplexer wird. Wenn Sie diese Befehle auf Poolebene ausführen, werden die Einstellungen nur für die Registrierungsrolle festgelegt, wenn in Ihrem Pool nicht alle Rollen enthalten sind (z. B. keine Webdienste). In diesem Fall werden Webdienste mit Einstellungen auf globaler Ebene verwendet, was ein verwirrendes Verhalten (insbesondere dann, wenn dies unbeabsichtigt erfolgt) sein kann.

Wenn ein Client die Registrierungseinstellungen aus einem Pool und die Webdiensteinstellungen aus einem anderen Pool verwendet und sich die Authentifizierungseinstellungen in einem inkonsistenten Zustand befinden, können sich Die Clients möglicherweise nicht anmelden.

Wenn für einen Pool nur eine Rolle vorhanden ist, gilt außerdem: 
* Set- wird nur die Einstellungen festlegen, die der vorhandenen Rolle entsprechen. Es wird keine besondere Warnung angezeigt, da einige Einstellungen *nicht festgelegt* wurden. 
* Get- gibt die Einstellung zurück, die der vorhandenen Rolle und den globalen Einstellungen für die rolle entspricht, die nicht vorhanden ist.
* Wenn keine rolle für einen Pool vorhanden ist, gibt sowohl Set- als auch Get- eine Fehlermeldung zurück.
* Wenn beide Rollen für einen Pool vorhanden sind, richtlinien jedoch nicht auf Poolebene definiert sind, gibt Get- eine Fehlermeldung zurück.

Es kann ratsam sein, für diese Werte ein Get- zu erstellen und den Startzustand zu screenshoten oder zu aufzeichnen, bevor Änderungen vorgenommen werden. Sie können auch erwägen, ein Protokoll mit Änderungen in oneNote zu speichern.

> [!NOTE]
> 
> Hinweis: Nach der Konfiguration von CsAuthConfig müssen Sie Enable-CsComputer Computer ausführen, damit die Einstellungen wirksam werden.

> [!IMPORTANT]
> Wenn Sie Lync Web Access (LWA) verwenden und formularbasierten Zugriff (Forms-Based Access, FBA) für den externen Zugriff verwenden müssen, konfigurieren Sie LWA neu, damit Clients mit Anonymer Zugriff darauf zugreifen können, um diese Szenarien zu unterstützen. Ebenso wird FBA nur für externe Benutzer blockiert, wenn Sie einwahl-Pin verwenden. Wenn sie ihren Pin ändern müssen, müssen sie sich intern bei ihrem Unternehmen anmelden.

> [!NOTE]
> 
> Wenn Sie den Parameter BlockWindowsAuthExternally verwenden, um NTLM extern zu blockieren, sollten Sie beachten, dass dadurch auch NTLM intern für den SIP-Kanal blockiert wird. Skype for Business- und Lync-Clients, die neuer als 2010 sind, können sich jedoch weiterhin anmelden, da sie NTLM über HTTP für die Anmeldung intern verwenden und dann ein Zertifikat abrufen, um sich über SIP anzumelden. Clients, die älter als 2010 sind, können sich in diesem Fall jedoch nicht intern anmelden, und Sie sollten ein Upgrade dieser Anwendungen in Betracht ziehen, damit Ihre Benutzer die sichere Funktionalität fortsetzen können.

> [!IMPORTANT] 
> Einige der Skype for Business-Webanwendungen unterstützen MA nicht. Wenn Sie also das Szenario BlockWindowsAuthExternallyAndInternally verwenden, können Sie nicht auf diese Anwendungen zugreifen. Anwendungen ohne MA-Unterstützung sind Webplaner, Einwahlseite, Skype for Business-Systemsteuerung (CSCP) und Seite mit den Reaktionsgruppeseinstellungen. 

## <a name="links"></a>Links 
- Weitere PowerShell-Informationen finden Sie unter:
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Weitere Informationen zur Verwendung der Befehle oder der cu, die für die Installation erforderlich sind, finden Sie unter:
    - [Cmdlets Briefing](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (Allgemein)
    - The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


