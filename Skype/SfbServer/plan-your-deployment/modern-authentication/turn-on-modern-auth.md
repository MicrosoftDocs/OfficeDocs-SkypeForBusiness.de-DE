---
title: Planen der internen und externen Authentifizierungsmethoden für das Netzwerk
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
ms.assetid: ''
description: In diesem Artikel werden Cmdlets erläutert, die Administratoren mehr Kontrolle über die innerhalb und außerhalb eines Unternehmens verwendeten Authentifizierungsmethoden bieten. Administratoren können Authentifizierungsmethoden intern oder extern für Ihr Netzwerk aktivieren oder deaktivieren.
ms.openlocfilehash: a3f26e0bb29a58b53547083a4410da849c054b03
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043717"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen, die vorversions Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren.

> [!NOTE]
> Wenn Sie diesen Artikel lesen möchten, sollten Sie bereits über die unterstützten modernen Authentifizierungs Topologien, Adal und über die moderne Authentifizierungskonfiguration Bescheid wissen, für den Fall, dass Sie dies nicht tun, sind hier die Artikel, die Sie zum Starten benötigen: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Die moderne Authentifizierung aktiviert nicht nur mehr sichere Authentifizierungsmethoden, wie die zweistufige Authentifizierung oder die zertifikatbasierte Authentifizierung, sondern kann auch die Autorisierung Ihres Benutzers durchführen, ohne dass Sie einen Benutzernamen oder ein Kennwort benötigen. Es ist ziemlich handlich.

Dieser Artikel hilft Ihnen, Bohrungen, die für DOS-Angriffe (Denial of Service) auf Skype for Business Servern verwendet wurden, zu schließen, indem Sie ältere Methoden, die für die Authentifizierung, extern, intern oder beides verwendet werden, in Ihrem Netzwerk deaktivieren. Eine gute Methode zum Beenden von DOS-Angriffen wäre beispielsweise das Deaktivieren der integrierten Windows-Authentifizierung (einschließlich NTLM und Kerberos). Wenn Sie NTLM extern deaktivieren und sich auf die zertifikatbasierte Authentifizierung verlassen, können Sie Kennwörter vor der Belichtung schützen. Dies liegt daran, dass NTLM Kennwortanmeldeinformationen verwendet, um Benutzer zu authentifizieren, aber die zertifikatbasierte Authentifizierung--aktiviert durch moderne auth--nicht. Das bedeutet, dass eine ideale Option zur Verringerung von DOS-Angriffen darin besteht, NTLM extern zu blockieren und stattdessen nur die zertifikatbasierte Authentifizierung zu verwenden.

In Ordnung, fangen wir an.

## <a name="what-would-you-be-changing"></a>Was würden Sie ändern? 

Diese Cmdlets funktionieren sowohl für SIP-als auch für Webdienste Points of Access. Obwohl für diese beiden Kanäle unterschiedliche Zugriffsmethoden verwendet werden, wobei der Gamut von NTLM und Kerberos bis zum anonymen Zugriff ausgeführt wird, wurden alle von Skype for Business verwendeten Standardmethoden berücksichtigt.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Abrufen der Cmdlets für Get-und setCsAuthConfigs

Diese Cmdlets werden nur nach dem kumulativen Update vom Juli 2018 (6.0.9319.534) für Microsoft Skype for Business Server 2015 installiert, und dann haben Sie eine Vielzahl von Topologien, die für Ihren Skype for Business-Server ein Roll-out möglich sind.

## <a name="topologies"></a>Topologien

Beachten Sie, dass es sich dabei um die unterstützten Topologien handelt, die an diesem Szenario beteiligt sind. Wenn Sie Unterstützung bei der Blockierung einer Methode benötigen, müssen Sie eine Konfiguration unter den folgenden Typen durchlaufen. 

> [!IMPORTANT]
> In der folgenden Tabelle und den Beschreibungen wird die *moderne Authentifizierung* als __MA__ abgekürzt, und die *integrierte Windows-Authentifizierung* wird als __Win__abgekürzt. Als Erinnerung stellt die integrierte Windows-Authentifizierung zwei Methoden zur Verfügung: NTLM und Kerberos-Authentifizierung. Sie müssen dies wissen, um die Tabelle ordnungsgemäß zu lesen!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Typ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Typ 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Beschreibung des Typs 1:__ Dies ist das Standardszenario, wenn __MA für Skype for Business Server aktiviert ist__ . Mit anderen Worten: Dies ist der *Ausgangspunkt* , wenn MA konfiguriert ist.

__Beschreibung des Typs 2:__ Diese Topologie blockiert NTLM *extern*, erlaubt jedoch NTLM oder Kerberos (für Clients, die Adal nicht unterstützen), *intern*zu arbeiten. Wenn Ihre Clients Adal unterstützen, werden Sie den MA intern verwenden.

__Typ 3 Beschreibung:__ Diese Topologie erfordert MA für alle Benutzer. Alle Ihre Adal-fähigen Clients funktionieren in dieser Topologie, und Kennwörter werden nicht genutzt, wenn Sie beispielsweise die Verwendung von Kennwörtern mit zertifikatbasierter Authentifizierung deaktivieren.

__Typ 4 Beschreibung:__ Diese Topologie blockiert NTLM *extern* und internes Ma. Sie ermöglicht *allen Clients* die *interne* Verwendung von vorversions Authentifizierungsmethoden (sogar Adal Clients).

__Beschreibung des Typs 5:__ *extern*verwenden ihre modernen Adal-Clients MA, und alle Clients, die Adal nicht unterstützen, verwenden die Vorversionen von Authentifizierungsmethoden. *Intern* verwenden jedoch *alle Clients* die Legacy Authentifizierung (einschließlich aller Adal-fähigen Clients).

Es ist ziemlich einfach, das Ziel des Schutzes ihrer Kennwörter in den verfügbaren Optionen zu verlieren. Beachten Sie, dass die ideale Situation darin besteht, MA extern zu verwenden (beispielsweisedurch Konfigurieren der zertifikatbasierten Authentifizierung), um DOS-Angriffe zu vermeiden. Wenn Sie es intern für ihre modernen Clients nutzen, werden Sie Ihr Netzwerk auch in Bezug auf Skype for Business Server DOS-Angriffe zukunftssicher machen.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für die Verwendung von "CsAuthConfig" auf globaler Ebene

Die `Set-CsAuthConfig` Konfiguration des Cmdlet-Effekts sowohl für die Registrierungsstelle als auch für die Webdienste Rollen.

Dieses Cmdlet sollte auf globaler Ebene auf dem Skype for Business Server ausgeführt werden. Es *kann* auf Poolebene ausgeführt werden, dies wird jedoch *nicht empfohlen* , da es die Komplexität Ihrer Installation erhöht. Wenn Sie diese Befehle auf Poolebene ausführen und Ihr Pool nicht über alle Rollen verfügt (beispielsweise nicht über Webdienste), werden die Einstellungen nur für die Rolle "Registrar" festgelegt. In diesem Fall führt Webdienste Einstellungen von der globalen Ebene aus, was verwirrend sein kann (insbesondere, wenn dies versehentlich geschieht).

Wenn ein Client die Registrierungseinstellungen aus einem Pool verwendet und die Webdienste Einstellungen aus einem anderen Pool und die Authentifizierungseinstellungen in einem inkonsistenten Zustand sind, können sich die Clients möglicherweise nicht anmelden.

Wenn für einen Pool nur eine Rolle vorhanden ist, gilt Folgendes: 
* Mit "festlegen" werden nur die Einstellungen festgelegt, die der vorhandenen Rolle entsprechen. Es wird keine spezielle Warnung ausgegeben, da einige Einstellungen *nicht* festgelegt wurden. 
* Get-gibt die Einstellung zurück, die der vorhandenen Rolle entspricht, und die globalen Einstellungen für die Rolle, die nicht vorhanden ist.
* Wenn keine der Rollen für einen Pool vorhanden ist, geben beide festlegen-und Get-eine Fehlermeldung zurück.
* Wenn beide Rollen für einen Pool vorhanden sind, aber Richtlinien nicht auf Poolebene definiert sind, gibt Get-eine Fehlermeldung zurück.

Es kann ratsam sein, eine Get-for diese Werte zu tun, und Screenshot oder Aufzeichnen Ihrer Startzustand, bevor Sie Änderungen vornehmen. Möglicherweise sollten Sie auch ein Protokoll der Änderungen in OneNote beibehalten.

> [!NOTE]
> 
> Hinweis: Nachdem Sie den CsAuthConfig konfiguriert haben, müssen Sie Enable-CsComputer auf jedem Computer ausführen, damit die Einstellungen wirksam werden.

> [!IMPORTANT]
> Wenn Sie lync-Webzugriff (LWA) verwenden und den formularbasierten Zugriff (FBA) für den externen Zugriff verwenden müssen, konfigurieren Sie LWA so neu, dass Clients mit anonymem Zugriff zur Unterstützung dieser Szenarien darauf zugreifen können. Wenn Sie eine Einwahl-PIN verwenden, wird FBA nur für externe Benutzer blockiert. Wenn Sie Ihre PIN ändern müssen, müssen Sie sich intern bei Ihrem Unternehmen anmelden.

> [!NOTE]
> 
> Wenn Sie den BlockWindowsAuthExternally-Parameter verwenden, um NTLM extern zu blockieren, beachten Sie, dass dies auch intern NTLM für den SIP-Kanal blockiert. Skype for Business-und lync-Clients, die neuer als 2010 sind, können sich jedoch weiterhin anmelden, da Sie NTLM über HTTP für SignIn verwenden und sich dann ein Zertifikat für die Anmeldung über SIP holen. Clients, die älter als 2010 sind, können sich in diesem Fall jedoch nicht intern anmelden, und Sie sollten diese Anwendungen möglicherweise aktualisieren, damit Ihre Benutzer die sichere Funktionalität wieder aufnehmen können.


## <a name="links"></a>Links 
- Weitere PowerShell-Informationen:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Gruppe-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Weitere Informationen zur Verwendung der Befehle oder der für die Installation erforderlichen Cu-Anweisungen:
    - [Cmdlets-Briefing](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (allgemein)
    - Die [Skype for Business Server 2015 vom Juli 2018, Core Components Cu](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
