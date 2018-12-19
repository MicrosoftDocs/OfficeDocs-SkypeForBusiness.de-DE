---
title: Planen von Authentifizierungsmethoden Legacy intern und extern in Ihr Netzwerk deaktivieren
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: In diesem Artikel Gliederungen-Cmdlets, mit denen Administratoren mehr Kontrolle über Authentifizierungsmethoden erhalten verwendet innerhalb und außerhalb, eines Unternehmens. Administratoren können Authentifizierungsmethoden auf Aktivieren oder deaktivieren Sie intern oder extern mit ihrem Netzwerk.
ms.openlocfilehash: 8350e1b6f3bae27c3b8355b0dee3b737bccaf655
ms.sourcegitcommit: bb4e7dec155dee358bec9d6e586730dae0b8f559
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "27371186"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planen der Legacy-Authentifizierungsmethoden intern und extern in Ihr Netzwerk zu deaktivieren.

> [!NOTE]
> Wenn Sie diesen Artikel lesen gerade, sollten Sie bereits kennen unterstützte modernen authentifizierungstopologien, ADAL, und zu modernen Authentifizierung Konfiguration, aber, falls dies nicht der Fall, hier sind die Artikel beginnen, müssen Sie: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Modernen Authentifizierung nicht nur sicherere Methoden der Authentifizierung, wie die zweistufige Authentifizierung oder zertifikatbasierte Authentifizierung aktivieren, ohne dass ein Benutzername und Kennwort zu können durchgeführt wird die Autorisierung des Benutzers. Es ist ziemlich praktisch.

In diesem Artikel helfen Ihnen beim Plug & Play-Lücken, die für Denial Of Service (DOS) Angriffe auf Skype for Business Server, indem Sie ältere Methoden für die Authentifizierung verwendet wird, extern, intern, deaktivieren oder beide in Ihr Netzwerk genutzt wurden haben. Eine gute Methode, um DOS-Angriffen beenden wäre beispielsweise die integrierte Windows-Authentifizierung zu deaktivieren (einschließlich NTLM und Kerberos). NTLM extern deaktivieren und zertifikatbasierte Authentifizierung der vertrauenden Seite hilft, um Kennwörter Belichtung zu schützen. Dies ist, da NTLM verwendet die Anmeldeinformationen zum Authentifizieren von Benutzern, aber nicht zertifikatbasierte Authentifizierung--durch moderne Auth – aktiviert. An, dass bedeutet, dass eine ideale Option zur Reduzierung von DOS-Angriffen extern Block NTLM und nur zertifikatbasierte Authentifizierung verwenden, stattdessen wird.

Alle Rechte, steigen.

## <a name="what-would-you-be-changing"></a>Was möchten Sie ändern? 

Diese Cmdlets Arbeit für SIP- und Webdienste Zugriffspunkte. Obwohl diese beiden Kanäle unterschiedliche Zugriffsmethoden verlaufende der Farbskala NTLM und Kerberos auf den anonymen Zugriff verwendet haben alle Standardmethoden von Skype für Unternehmen verwendeten berücksichtigt wurden.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Wie Sie die Cmdlets Get - und Set-CsAuthConfig abrufen

Diese Cmdlets wird nur installiert buchen Juli 2018 Kumulatives Update (6.0.9319.534) für Microsoft Skype für Business Server 2015, und Sie dann eine Vielzahl von Topologien, die für Ihre Skype für Business Server gemacht werden kann.

## <a name="topologies"></a>Topologien

Es ist wichtig zu beachten, dass dies die unterstützten Topologien in diesem Szenario sind! Wenn Sie an den Support finden Sie Informationen zum Sperren einer Methode müssen, beispielsweise müssen Sie die Konfiguration eines zwischen den folgenden Typen aufweisen. 

> [!IMPORTANT]
> In der Tabelle und die Beschreibung unten *Moderne Authentifizierung* wird als __MA__ abgekürzt und *Integrierte Windows-Authentifizierung* wird als __gewinnen__abgekürzt. Als Erinnerung, integrierte Windows-Authentifizierung besteht aus zwei Methoden: NTLM und Kerberos-Authentifizierung. Sie müssen wissen, diese Option, um die Tabelle nicht ordnungsgemäß lesen!


|       |Extern  |Intern  |Parameter  |
|---------|:---------|:---------|---------|
|__Geben Sie 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Typ 2__   |  VERWALTUNGS-AGENT       | MA + Win         | BlockWindowsAuthExternally        |
|__Typ 3__   |  VERWALTUNGS-AGENT       | VERWALTUNGS-AGENT        | BlockWindowsAuthExternallyAndInternally        |
|__Typ 4__   |  VERWALTUNGS-AGENT       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Geben Sie 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Geben Sie 1 Beschreibung:__ Dies ist die Standardeinstellung __Szenario für MA ist für eingeschaltet Skype für Business Server__ . Anders ausgedrückt, ist dies der *Ausgangspunkt* Wenn MA konfiguriert ist.

__2 Beschreibung:__ Diese Topologie NTLM *extern*blockiert, ermöglicht aber auch NTLM oder Kerberos (für Clients, die ADAL nicht unterstützen), *intern*funktioniert. Wenn Ihre Clients ADAL unterstützen wird MA intern verwendet.

__3 Beschreibung:__ Diese Topologie erfordert Verwaltungs-Agent für alle Benutzer. Alle ADAL-fähige Clients funktionieren in dieser Topologie und Kennwörter werden nicht genutzt werden, wenn Sie beispielsweise die Verwendung von Kennwörtern mit AUTH zertifikatbasierte deaktivieren

__4 Beschreibung:__ Diese Topologie blockiert NTLM *extern* und MA intern. Sie können *Alle Clients* verwenden ältere Authentifizierung Methoden *intern* (sogar ADAL-fähige Clients).

__5 Beschreibung:__ *Extern*, den modernen ADAL Clients MA verwendet werden, und alle Clients, die keine ADAL unterstützen ältere Authentifizierungsmethoden verwenden. Aber *intern* *Alle Clients* verwenden ältere Authentifizierung (einschließlich aller ADAL-fähige Clients).

Es ist ziemlich einfach Nachverfolgen des Ziels der Schutz von Kennwörtern in den verfügbaren Optionen verloren gehen. Beachten Sie die ideale Situation ist die Verwendung MA extern (beispielsweise durch Konfigurieren von zertifikatbasierte Authentifizierung), um DOS-Angriffe zu verhindern. Wenn Sie es intern für moderne Clients nutzen, müssen Sie auch die Zukunft vor Ihrem Netzwerk zu Skype für Business Server DOS-Angriffe.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Gründe für das Set-CsAuthConfig auf globaler Ebene verwenden

Die `Set-CsAuthConfig` Cmdlet Effekte Konfiguration auf die Registrierung und die Webdienste Rollen.

Dieses Cmdlet auf globaler Ebene von Ihrer Skype für Business Server ausgeführt werden soll. Sie *können* auf der Poolebene jedoch also *nicht empfohlen* ausgeführt werden, da es Komplexität Ihrer Installation hinzufügen möchten. Durch diese Befehle auf der Poolebene ausführen, wenn auf der Pool alle Rollen enthalten ist (beispielsweise keinen Webdienste), die Einstellungen werden nur für die Registrierung Rolle festgelegt werden. In diesem Fall wird Webdienste mit Einstellungen aus der globalen Ebene, fortzusetzen, die verwirrend Verhalten (besonders wenn dies versehentlich erfolgt) sein kann.

Wenn ein Client für die Registrierung von einem Pool und Einstellungen für Webdienste aus einer anderen Pool verwendet, und die Authentifizierungseinstellungen inkonsistent sind, möglicherweise Yous Clients nicht anmelden.

Auch wenn nur eine Rolle, die für einen Pool vorhanden ist: 
* Set-wird legen Sie die Einstellungen entsprechen, die nur auf die Rolle, die vorhanden ist. Keine besondere Warnung erhalten, da einige Einstellungen *nicht* festgelegt wurden. 
* Get-wird zurückgegeben, die Einstellung, die die Rolle entspricht, die vorhanden ist, und die globalen Einstellungen für die Rolle, die nicht vorhanden ist.
* Wenn keine Rolle für einen Pool vorhanden ist, gibt beide Set und Get-wird eine Fehlermeldung zurück.
* Wenn beide Rollen für einen Pool vorhanden sind, aber Richtlinien nicht auf Pool-Ebene definiert, Get-wird ein Fehler zurückgegeben.

Möglicherweise führen Sie eine Get-für diese Werte und Screenshot oder notieren Sie ihre Anfangszustand vor jeder Änderung Listenelementen. Sie sollten auch ein Protokoll der Änderungen in einem OneNote beibehalten.

> [!IMPORTANT]
> Wenn Sie Lync Web Access (LWA) verwenden, Forms-based Access (FBA), für den externen Zugriff verwenden müssen konfigurieren Sie LWA, damit Clients mit anonymem Zugriff auf diese Szenarien unterstützen zugreifen können. Dienstanbieter entscheidet auch, wenn Sie die Einwahl-Pin verwenden, FBA für externe Benutzer nur blockiert. Wenn sie ihre Pin ändern müssen, müssen sie ihre Corporation dazu intern Anmeldung.

## <a name="links"></a>Links 
- Für Weitere Informationen zu PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Für weitere Richtung zum Verwenden der Befehle oder auf die CU erforderlich, um diese zu installieren:
    - [Cmdlets für briefing](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Updates für Skype für Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) (Allgemein)
    - Die [Juli 2018 Skype für Business Server 2015 Kernkomponenten CU](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
