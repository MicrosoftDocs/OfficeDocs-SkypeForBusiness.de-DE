---
title: Planen, Legacy Authentifizierungsmethoden intern und extern für Ihr Netzwerk zu deaktivieren
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In diesem Artikel werden Cmdlets erläutert, die Administratoren mehr Kontrolle über Authentifizierungsmethoden ermöglichen, die innerhalb und außerhalb eines Unternehmens verwendet werden. Administratoren können Authentifizierungsmethoden intern oder extern an Ihr Netzwerk aktivieren oder deaktivieren.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297267"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen Sie das Deaktivieren von Legacy Authentifizierungsmethoden intern und extern für Ihr Netzwerk.

> [!NOTE]
> Wenn Sie diesen Artikel lesen möchten, sollten Sie sich bereits mit unterstützten modernen Authentifizierungs Topologien, Adal und der modernen Authentifizierungskonfiguration vertraut machen, für den Fall, dass Sie dies nicht tun, sollten Sie die folgenden Artikel ausführen: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Die moderne Authentifizierung ermöglicht nicht nur sicherere Authentifizierungsmethoden, wie etwa zweistufige auth-oder zertifikatbasierte Authentifizierung, sondern kann auch die Autorisierung Ihres Benutzers durchführen, ohne dass ein Benutzername oder Kennwort erforderlich ist. Das ist ziemlich praktisch.

Dieser Artikel soll Ihnen helfen, Löcher zu stopfen, die für Denial-of-Service-Angriffe (DOS) auf Skype for Business-Servern genutzt wurden, indem Sie ältere Methoden, die für die Authentifizierung verwendet werden, extern, intern oder beides, in Ihrem Netzwerk deaktivieren. Eine gute Methode zur Unterstützung von DOS-Angriffen wäre beispielsweise das Deaktivieren der integrierten Windows-Authentifizierung (einschließlich NTLM und Kerberos). Das Deaktivieren von NTLM extern und das Vertrauen auf die zertifikatbasierte Authentifizierung hilft, Kennwörter vor Gefährdungen zu schützen. Dies liegt daran, dass NTLM Kennwort-Anmeldeinformationen verwendet, um Benutzer zu authentifizieren, aber die zertifikatbasierte Authentifizierung, die durch moderne auth-Funktion aktiviert ist, nicht. Das bedeutet, dass eine ideale Möglichkeit zum Verringern von DOS-Angriffen darin besteht, NTLM extern zu blockieren, und stattdessen nur zertifikatbasierte Authentifizierung zu verwenden.

Alles klar, lasst uns loslegen.

## <a name="what-would-you-be-changing"></a>Was würden Sie ändern? 

Diese Cmdlets funktionieren sowohl für SIP-als auch für Webdienste-Zugriffspunkte. Obwohl diese beiden Kanäle unterschiedliche Zugriffsmethoden verwenden und den Gamut von NTLM und Kerberos bis zum anonymen Zugriff ausführen, wurden alle von Skype for Business verwendeten Standardmethoden berücksichtigt.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Abrufen der Get-und CsAuthConfig-Cmdlets

Diese Cmdlets werden nur nach dem kumulativen Update vom Juli 2018 (6.0.9319.534) für Microsoft Skype for Business Server 2015 installiert, und Sie verfügen über eine Vielzahl von Topologien, die für Ihren Skype for Business-Server bereitgestellt werden können.

## <a name="topologies"></a>Topologien verfügen

Beachten Sie, dass dies die unterstützten Topologien sind, die in diesem Szenario involviert sind. Wenn Sie zum Beispiel Hilfe beim Blockieren einer Methode benötigen, benötigen Sie eine Konfiguration zwischen den folgenden Typen. 

> [!IMPORTANT]
> In der folgenden Tabelle und den Beschreibungen wird die *moderne Authentifizierung* als " __MA__ " abgekürzt und die *integrierte Windows-Authentifizierung* als " __Win__" abgekürzt. Zur Erinnerung: die integrierte Windows-Authentifizierung besteht aus zwei Methoden: NTLM-und Kerberos-Authentifizierung. Sie müssen dies wissen, um die Tabelle richtig zu lesen!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Typ 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  MA       | Gewinnen        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Typ 5__   |  MA + Win       | Gewinnen        | BlockModernAuthInternally         |

__Beschreibung des Typs 1:__ Dies ist das Standardszenario, wenn MA für ____ Skype for Business Server aktiviert ist. Anders ausgedrückt: Dies ist der *Ausgangspunkt* , an dem MA konfiguriert ist.

__Beschreibung des Typs 2:__ Diese Topologie blockiert NTLM *extern*, ermöglicht aber NTLM oder Kerberos (für Clients, die Adal nicht unterstützen), *intern*zu arbeiten. Wenn Ihre Clients Adal unterstützen, wird MA intern verwendet.

__Beschreibung des Typs 3:__ Für diese Topologie ist MA für alle Benutzer erforderlich. Alle Ihre Adal-fähigen Clients funktionieren in dieser Topologie, und Kennwörter werden nicht genutzt, wenn Sie beispielsweise die Verwendung von Kennwörtern mit zertifikatbasierter Authentifizierung deaktivieren.

__Beschreibung des Typs 4:__ Diese Topologie blockiert NTLM *extern* und intern für Ma. Damit können *alle Clients* *intern* Legacy Authentifizierungsmethoden verwenden (sogar Adal-fähige Clients).

__Beschreibung des Typs 5:__ *Extern*werden ihre modernen Adal-Clients MA verwenden, und alle Clients, die Adal nicht unterstützen, verwenden Legacy Authentifizierungsmethoden. *Intern* verwenden jedoch *alle Clients* die Legacy Authentifizierung (einschließlich aller Adal-fähigen Clients).

Es ist ziemlich einfach, den Überblick über das Ziel zu verlieren, ihre Kennwörter in den verfügbaren Optionen zu schützen. Beachten Sie, dass die ideale Situation darin besteht, MA extern zu verwenden (beispielsweisedurch Konfigurieren der zertifikatbasierten Authentifizierung), um DOS-Angriffe zu vermeiden. Wenn Sie es intern für ihre modernen Kunden nutzen, werden Sie auch in Zukunft Ihr Netzwerk in Bezug auf Skype for Business Server DOS-Angriffe schützen.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für die Verwendung von "Satz-CsAuthConfig" auf globaler Ebene

Die `Set-CsAuthConfig` Cmdlet-Effekt Konfiguration sowohl für die Registrierungsstelle als auch für die Webdienste-Rollen.

Dieses Cmdlet soll auf globaler Ebene Ihres Skype for Business-Servers ausgeführt werden. Sie *kann* auf der Poolebene ausgeführt werden, wird aber *nicht empfohlen* , da Sie die Komplexität Ihrer Installation erhöht. Wenn Sie diese Befehle auf der Poolebene ausführen, wenn Ihr Pool nicht alle Rollen enthält (beispielsweise keine Webdienste), werden die Einstellungen nur für die Registrierungsstelle-Rolle eingestellt. In diesem Fall werden Webdienste mit Einstellungen von der globalen Ebene weitergeführt, was verwirrend sein kann (insbesondere, wenn dies unbeabsichtigt erfolgt).

Wenn ein Client die Registrierungsstellen Einstellungen aus einem Pool und die Webdiensteinstellungen aus einem anderen Pool verwendet und sich die Authentifizierungseinstellungen in einem inkonsistenten Zustand befinden, können sich Yous-Clients möglicherweise nicht anmelden.

Wenn für einen Pool nur eine Rolle vorhanden ist, gilt Folgendes: 
* Mit "festlegen" werden nur die Einstellungen festgesetzt, die der vorhandenen Rolle entsprechen. Es wird keine besondere Warnung ausgegeben, da einige Einstellungen *nicht* eingestellt wurden. 
* Get-gibt die Einstellung zurück, die der Rolle entspricht, die vorhanden ist, und die globalen Einstellungen für die Rolle, die nicht vorhanden ist.
* Wenn für einen Pool keine Rolle vorhanden ist, gibt sowohl die Einstellung als auch die Get-Funktion eine Fehlermeldung zurück.
* Wenn beide Rollen für einen Pool vorhanden sind, die Richtlinien aber nicht auf der Poolebene definiert sind, gibt Get-eine Fehlermeldung zurück.

Es ist möglicherweise am klügsten, eine Get-für diese Werte und Screenshot oder Aufzeichnen Ihres Anfangszustands, bevor Sie Änderungen vornehmen. Möglicherweise sollten Sie auch ein Protokoll der Änderungen in OneNote speichern.

> [!NOTE]
> 
> Hinweis: Nachdem Sie die CsAuthConfig konfiguriert haben, müssen Sie Enable-CsComputer auf jedem Computer ausführen, damit die Einstellungen wirksam werden.

> [!IMPORTANT]
> Wenn Sie lync Web Access (LWA) verwenden und den formularbasierten Zugriff (FBA) für den externen Zugriff verwenden müssen, konfigurieren Sie LWA neu, damit Clients mit anonymem Zugriff darauf zugreifen können, um diese Szenarien zu unterstützen. Wenn Sie die Einwahl-PIN verwenden, wird FBA nur für externe Benutzer blockiert. Wenn Sie Ihre PIN ändern müssen, müssen Sie sich intern bei Ihrem Unternehmen anmelden.

## <a name="links"></a>Links 
- Weitere PowerShell-Informationen:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Satz-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Für weitere Informationen zur Verwendung der Befehle oder des für die Installation erforderlichen CU:
    - [Cmdlets-Unterrichtung](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) Allgemein
    - Der [Juli 2018 Skype for Business Server 2015, Core Components Cu](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
