---
title: Planen von einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Zusammenfassung: Lesen Sie dieses Thema zu erfahren Sie mehr über das Planen von einwahlkonferenzen in Skype für Business Server.'
ms.openlocfilehash: 6df8e06ecbbf6da67d34b7b6332ed2f2ca93e50c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885511"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planen von einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren Sie einwahlkonferenzen in Skype für Business Server planen.
  
Einwahlkonferenzen ist eine optionale Funktion von Skype für Business Server, der Besprechungsteilnehmer für die Audiodaten in einer Besprechung beitreten, indem Sie die Besprechung einwählen, über ein Telefon ermöglicht. Einwahlkonferenzen sind ein Unterbereich der Audiokonferenzen und müssen zusätzlich konfiguriert werden. In diesem Abschnitt wird beschrieben, was Sie berücksichtigen müssen, bevor Sie Einwahlkonferenzen für Ihre Organisation einrichten. 
  
Einige der Komponenten für einwahlkonferenzen erforderlich sind spezifisch für einwahlkonferenzen und einige Komponenten von Enterprise-VoIP. Wenngleich Einwahlkonferenzen einige Komponenten von Enterprise Voice verwenden, ist die Bereitstellung von Enterprise Voice nicht erforderlich, um Einwahlkonferenzen bereitzustellen. In diesem Abschnitt werden die Komponenten beschrieben, die Sie für Einwahlkonferenzen benötigen. Weitere Informationen zum Planen einer vollständigen Enterprise-VoIP-Lösung finden Sie unter [Planen Ihrer Enterprise-VoIP-Lösung in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
Um Einwahlkonferenzen nutzen zu können, müssen Sie über einen Vermittlungsserver eine Telefonfestnetz-Verbindung (Public Switched Telephone Network) einrichten. Darüber hinaus müssen Sie die folgenden Aspekte berücksichtigen, bevor Sie Einwahlkonferenzen in Ihrer Organisation zulassen:
  
- Ihren Plan für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN)
    
- Ihren Plan für Wähleinstellungen, Zugriffsnummern und Konferenzregionen
    
- Ihren Plan für die Erstellung von Konferenzverzeichnissen
    
- Ihre Konferenzrichtlinie für den Zugriff per Einwahl
    
- Unterstützung für Unternehmens- und anonyme Benutzer
    
> [!NOTE]
> Wenn Sie einwahlkonferenzen bereitstellen, müssen Sie es in jedem Pool bereitstellen, auf dem Sie Skype für Business Server Konferenzen bereitstellen. Sie müssen nicht jedem Pool Zugriffsnummern zuweisen (die Nummern, die Teilnehmer wählen, um einer Konferenz beizutreten), aber Sie müssen die Einwahl-Funktion in jedem Pool bereitstellen. Diese Anforderung unterstützt die Aufzeichnung Ihres Namens-Funktion, wenn ein Benutzer von einem Pool einen Skype für Business Server-Konferenz in einen anderen Pool Teilnahme an eine Zugriffsnummer aufruft. 
  
## <a name="plan-for-pstn-connectivity"></a>Planen der PSTN-Konnektivität

Für Einwahlkonferenzen sind mindestens ein Vermittlungsserver und ein PSTN-Gateway (Public Switched Telephone Network, Festnetz) erforderlich. 
  
Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort kann ein Vermittlungsserver in einem Front-End-Pool oder auf einem Standard Edition-Server ausgeführt oder auf einem eigenständigen Server oder in einem eigenständigen Pool bereitgestellt werden. An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch Appliance bereitstellen.
  
Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder als Komponente der Survivable Branch Appliance eingesetzt werden.
  
Ausführliche Informationen zu Vermittlungsserver und PSTN-gatewayanforderungen finden Sie unter [Mediation Server Component in Skype für Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)und [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md) [Definieren eines Gateways im Topologie Generator in Skype für Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planen von Wähleinstellungen, Zugriffsnummern und Konferenzregionen

Zum Konfigurieren von Einwahlkonferenzen erstellen Sie Wähleinstellungen und Zugriffsnummern zum Einwählen. Außerdem vergeben Sie Einwahlregionen, über die eine Zugriffsnummer den entsprechenden Wähleinstellungen zugewiesen wird. Genauer gesagt:
  
- Wähleinstellungen sind Sätze von Normalisierungsregeln, in welchen die Anzahl und das Muster von Ziffern in einer Telefonnummern festgelegt wird und die die Telefonnummer in das zur Anrufweiterleitung erforderliche Standard-E.164-Format übersetzen.
    
- Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.
    
- Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. 
    
- Jeder Satz von Wähleinstellungen ist einer Konferenzregion zugeordnet.
    
Wenn Sie einen Satz von Wähleinstellungen erstellen, geben Sie die Region für Einwahlkonferenzen an, für die diese Wähleinstellungen gelten. Wenn Sie anschließend die Zugriffsnummern zum Einwählen erstellen, wählen Sie die Region aus, die ihrerseits die Zugriffsnummern den geeigneten Wähleinstellungen zuordnet.
  
Außerdem geben Sie den Gültigkeitsbereich der Wähleinstellungen an: Benutzer, Pool oder Standort. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen. 
  
Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:
  
- Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.
    
- Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.
    
- Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.
    
- Standardmäßig sind in der Besprechungseinladung alle Einwahlnummern für die Region enthalten.
    
- Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Wenn Benutzer Outlook verwenden, um eine Besprechung planen, verwendet der Benutzer das Onlinebesprechungs-Add-in für Skype für Unternehmen so ändern Sie die Region).
    
- Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.
    
- Sie können die Reihenfolge, in der Zugriffsnummern innerhalb einer Region auf der Seite Zugriffsnummer für Einwahl-Konferenzeinstellungen werden angezeigt (und somit die Reihenfolge, in der sie in der konferenzeinladung angezeigt werden) mithilfe von Skype für Business Server-Verwaltungsshell-Cmdlets konfigurieren.
    
- Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.
    
Weitere Informationen zum Erstellen eines Wählplans finden Sie unter [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) und [Erstellen oder Ändern einer Normalisierungsregel in Skype für Business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planen von Konferenzverzeichnissen

Konferenzverzeichnisse verwalten eine Zuordnung zwischen alphanumerische besprechungs-ID, die ein Teilnehmer an einer Konferenz teilnehmen, bei Verwendung von Skype für Unternehmen verwendet und die numerische Konferenz-ID, einwahlkonferenzen Teilnehmer an der Konferenz teilnehmen. Das Format der Konferenz-ID lautet folgendermaßen:
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Wenn diese Richtlinie eingehalten wird, bleiben die Konferenz-IDs in der Regel kurz. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) 9 übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planen einer Konferenzrichtlinie für den Zugriff per Einwahl

Beim Konfigurieren von konferenzrichtlinien, müssen Konferenzen für DFÜ-Zugriff aktiviert sein. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:
  
- eine numerische Konferenz-ID, die zur Identifizierung der Konferenz dient
    
- mindestens eine PSTN-Zugriffsnummer
    
- einen Link zur Einrichtungsseite für Einwahlkonferenzen, die eine vollständige Liste der Zugriffsnummern mit den zugehörigen Sprachen enthält; eine Möglichkeit zum Erstellen, Zurücksetzen und Aufheben der Sperrung von PINs (Personal Identification Number) sowie andere Informationen wie z. B. DTMF-Steuerelemente (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren)
    
Weitere Informationen zu konferenzrichtlinien finden Sie unter [Configure einwahlkonferenzen in Skype für Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) und [konferenzrichtlinien in Skype für Business Server verwalten](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Unterstützung für Unternehmens- und anonyme Benutzer

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Enterprise-Benutzer werden Active Directory-Domänendienste-Anmeldeinformationen und Skype für Business Server-Konten in ihrer Organisation. Anonyme Benutzer verfügen über keine Anmeldeinformationen innerhalb Ihrer Organisation. Ein Benutzer in der Organisation eines verbundpartners, der das Telefonfestnetz verwendet für die Verbindung zu einer Konferenz wird im Kontext einwahlkonferenzen wie ein anonymer Benutzer behandelt. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.
  
Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. Der Front-End-Server verwendet die Kombination aus der vollständigen Telefonnummer oder Durchwahl und der PIN, um Unternehmensbenutzer eindeutig ihren Active-Anmeldeinformationen zuzuordnen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.
  
> [!NOTE]
> Unternehmensbenutzer, die sich aus einer IP-Telefon (geschäftlich) oder von Skype für Business Server Attendant einwählen werden nicht ihrer Telefonnummer aufgefordert, da sie bereits authentifiziert sind. 
  
Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.
  
> [!NOTE]
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt. 
  
Bei der Planung einer Besprechung kann sich der Besprechungsorganisator entscheiden, den Zugriff auf die Besprechung einzuschränken, indem er eine geschlossene oder gesperrte Besprechung anlegt. In diesem Fall müssen sich die Benutzer bei der Einwahl authentifizieren. 
  
- Benutzer, die sich bei der Einwahl nicht authentifizieren können oder wollen, werden in die Lobby verschoben, bis der Leiter sie akzeptiert oder ablehnt, oder der Timeout läuft ab und sie werden getrennt.
    
- Sobald Einwahlbenutzer zu einer Konferenz zugelassen wurden, können sie am Audioteil der Konferenz teilnehmen und über das Tastenfeld ihres Telefons DTMF-Befehle (Dual-Tone Multi-Frequency, Mehrfrequenzverfahren) eingeben.
    
- Der Leiter einer Einwahlkonferenz kann mithilfe von DTMF-Befehlen die Möglichkeit der Teilnehmer zur Stummschaltung ein- oder ausschalten, die Konferenz sperren oder entsperren, Personen aus der Lobby aufnehmen sowie Ankündigungen bei Zu- und Abgang ein- bzw. ausschalten.
    
- Konferenzleiter können mithilfe von DTMF-Befehlen zudem alle Teilnehmer aus der Lobby zulassen. Durch diese Aktion werden die Berechtigungen für die Besprechung so geändert, dass anschließend sämtliche Benutzer zugelassen werden, die der Besprechung beitreten. 
    
- Alle eingewählten Teilnehmer können DTMF-Befehle ausführen, um Hilfeinformationen abzuhören, die Namen der Teilnehmer wiederzugeben und sich selbst stumm zu schalten.
    
- Für eingewählte Teilnehmer werden unabhängig davon, ob sie sich über das Festnetz einwählen oder nicht, während der Konferenz persönliche Ansagen wiedergegeben. Diese Informationen umfassen z. B., ob die Teilnehmer stumm geschaltet wurden, ob die Besprechung aufgezeichnet wird oder ob Benutzer in der Lobby warten.
    
    > [!NOTE]
    > Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben. 
  

