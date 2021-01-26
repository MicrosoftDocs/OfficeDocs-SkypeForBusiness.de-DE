---
title: Planen von Einwahlkonferenzen in Skype for Business Server
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
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Zusammenfassung: In diesem Thema erfahren Sie mehr über die Planung von Einwahlkonferenzen in Skype for Business Server.'
ms.openlocfilehash: 31e422a07c34eaf17c09157c2e12ad843dbacb03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814005"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planen von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie mehr über die Planung von Einwahlkonferenzen in Skype for Business Server.
  
Einwahlkonferenzen sind eine optionale Funktion von Skype for Business Server, mit der Besprechungsteilnehmer am Audioteil einer Besprechung teilnehmen können, indem sie sich über ein Telefon in die Besprechung einwählen. Einwahlkonferenzen sind ein Teil von Audiokonferenzen und erfordern zusätzliche Konfiguration. In diesem Thema wird beschrieben, was Sie sich vor der Bereitstellung von Einwahlkonferenzen für Ihre Organisation überlegen müssen. 
  
Einige der für Einwahlkonferenzen erforderlichen Komponenten sind spezifisch für Einwahlkonferenzen, andere sind Enterprise-VoIP Komponenten. Obwohl für Einwahlkonferenzen einige der komponenten verwendet werden, die Enterprise-VoIP verwendet, können Sie Einwahlkonferenzen auch dann bereitstellen, wenn Sie keine Enterprise-VoIP. In diesem Abschnitt werden die Komponenten beschrieben, die für Einwahlkonferenzen erforderlich sind. Weitere Informationen zum Planen einer vollständigen lösung Enterprise-VoIP finden Sie unter [Plan your Enterprise-VoIP solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
Für Einwahlkonferenzen müssen Sie über einen Vermittlungsserver eine Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN) bereitstellen. Zusätzlich zur Bereitstellung eines Vermittlungsservers müssen Sie Folgendes berücksichtigen, um Einwahlkonferenzen für Ihre Organisation zu ermöglichen:
  
- Ihr Plan für die Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN)
    
- Ihr Plan für Wählpläne, Zugriffsnummern und Konferenzregionen
    
- Planen der Erstellung von Konferenzverzeichnissen
    
- Ihre Konferenzrichtlinie zum Zulassen des Zugriffs auf die Einwahl
    
- Unterstützung für Unternehmensbenutzer und anonyme Benutzer
    
> [!NOTE]
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie sie in jedem Pool bereitstellen, in dem Sie Skype for Business Server-Konferenzen bereitstellen. Sie müssen nicht in jedem Pool Zugriffsnummern zuweisen – die Nummern, die Teilnehmer anrufen, um an einer Konferenz teil zu nehmen – aber Sie müssen die Einwahlfunktion in jedem Pool bereitstellen. Diese Anforderung unterstützt die Funktion für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool anruft, um an einer Skype for Business Server-Konferenz in einem anderen Pool teil zu nehmen. 
  
## <a name="plan-for-pstn-connectivity"></a>Planen der Festnetzanbindung

Für Einwahlkonferenzen sind mindestens ein Vermittlungsserver und mindestens ein PstN-Gateway (Public Switched Telephone Network) erforderlich. 
  
Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort können Sie einen Vermittlungsserver mit einem Front-End-Pool oder Standard Edition-Server verbinden oder ihn auf einem eigenständigen Server oder Pool bereitstellen. An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch Appliance bereitstellen.
  
Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständiges Gateway oder eine Komponente der Survivable Branch Appliance sein.
  
Weitere Informationen zu den Anforderungen für Vermittlungsserver und PSTN-Gateways finden Sie unter "Vermittlungsserverkomponente" [in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), Bereitstellen eines Vermittlungsservers im [Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)und Definieren eines Gateways im [Topologie-Generator in Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planen von Wählplänen, Zugriffsnummern und Konferenzregionen

Zum Konfigurieren von Einwahlkonferenzen erstellen Sie Wählpläne und Zugriffsnummern für Einwahlkonferenzen. Außerdem geben Sie die Einwahlregionen an, die den Wählplänen eine Zugriffsnummer für Einwahlkonferenzen zuordnen. Das bedeutet im Detail:
  
- Wählpläne sind Sätze von Normalisierungsregeln, die die Nummer und das Muster von Ziffern in einer Telefonnummer angeben und die Telefonnummer in das standard E.164-Format übersetzen, das für die Anrufrouting erforderlich ist.
    
- Zugriffsnummern für Einwahlkonferenzen sind die Nummern, die Benutzer zur Teilnahme an Konferenzen wählen.
    
- Jede Zugriffsnummer für Einwahlkonferenzen muss mindestens einem Satz mit Wähleinstellungen zugeordnet sein. 
    
- Jeder Wählplan ist einer Konferenzregion zugeordnet.
    
Wenn Sie einen Wählplan erstellen, geben Sie die Region für Einwahlkonferenzen an, die für den Wählplan gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.
  
Sie geben auch den Bereich des Wählplans an: Benutzerbereich, Poolbereich oder Standortbereich. Jedem Benutzer werden die Wähleinstellungen aus dem am engsten gefassten Gültigkeitsbereich zugeordnet, der für den Benutzer gilt. Beispielsweise werden dem Benutzer Wähleinstellungen auf Benutzerebene zugewiesen, falls solche gelten. Gelten keine Wähleinstellungen auf Benutzerebene, werden dem Benutzer Wähleinstellungen auf Poolebene zugewiesen. Gelten keine Wähleinstellungen auf Poolebene, werden dem Benutzer Wähleinstellungen auf Standortebene zugewiesen. Gelten keine Wähleinstellungen auf Standortebene, werden dem Benutzer die globalen Wähleinstellungen zugewiesen. 
  
Bevor Sie die Wähleinstellungen konfigurieren, ist es wichtig zu planen, wie die Regionen benannt und verwendet werden sollen. Für die Regionen von Einwahlkonferenzen gelten folgende Überlegungen:
  
- Eine Region ist in der Regel ein geografischer Bereich, der einem Büro oder einer Gruppe von Büros zugeordnet wird.
    
- Den Einwahlnummern werden Sprachen zugeordnet. Wenn Sie geografische Bereiche mit mehreren Sprachen unterstützen, sollten Sie entscheiden, wie die Regionen für die Unterstützung der verschiedenen Sprachen definiert werden sollen. Beispielsweise können Sie mehrere Regionen basierend auf einer Kombination aus Geografie und Sprache definieren, oder Sie können eine einzige Region basierend auf der Geografie definieren und für jede Sprache eine eigene Einwahlnummer verwenden.
    
- Wenn ein Benutzer eine Besprechung plant, wird für die Besprechung standardmäßig die Region verwendet, die durch die Wähleinstellungen des Benutzers festgelegt ist.
    
- Standardmäßig sind alle Einwahlnummern für die Region in der Besprechungseinladung enthalten.
    
- Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Wenn Benutzer Outlook zum Planen einer Besprechung verwenden, verwendet der Benutzer das Online-Besprechungs-Add-In für Skype for Business, um die Region zu ändern).
    
- Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.
    
- Mithilfe von Skype for Business Server Management Shell-Cmdlets können Sie die Reihenfolge konfigurieren, in der Zugriffsnummern innerhalb einer Region auf der Seite mit den Einstellungen für Einwahlkonferenzen angezeigt werden (und damit die Reihenfolge, in der sie in der Konferenzeinladung angezeigt werden).
    
- Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.
    
Weitere Informationen zum Erstellen eines Wählplans finden Sie unter Erstellen oder Ändern eines Wählplans [in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) und Erstellen oder Ändern einer Normalisierungsregel in Skype for [Business.](../../deploy/deploy-enterprise-voice/normalization-rules.md) 
  
## <a name="plan-for-conference-directories"></a>Planen von Konferenzverzeichnissen

In Konferenzverzeichnissen wird eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer verwendet, um bei Verwendung von Skype for Business an einer Konferenz teil zu nehmen, und der nur numerischen Konferenz-ID, die ein Einwahlkonferenzteilnehmer zum Beitreten zur Konferenz verwendet, beibehalten. Das Format der Konferenz-ID lautet folgendermaßen:
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Anhand dieser Richtlinie können die Konferenz-IDs im Allgemeinen klein gehalten werden. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planen einer Konferenzrichtlinie, die den Zugriff auf die Einwahl zulässt

Konferenzen müssen für den Einwahlzugriff aktiviert sein, wenn Sie Konferenzrichtlinien konfigurieren. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:
  
- Eine numerische Konferenz-ID, die die Konferenz identifiziert
    
- Eine oder mehrere PSTN-Zugriffsnummern
    
- Ein Link zu einer Seite mit Einstellungen für Einwahlkonferenzen, die eine vollständige Liste der Zugriffsnummern mit den zugehörigen Sprachen enthält; einen Ort zum Erstellen, Zurücksetzen oder Aufheben der Blockierung von persönlichen Identifikationsnummern (PINs); und andere Informationen, z. B. Dual-Tone Multi-Frequency (DTMF)-Steuerelemente
    
Weitere Informationen zu Konferenzrichtlinien finden Sie unter "Konfigurieren von Einwahlkonferenzen [in Skype for Business Server"](../../deploy/deploy-conferencing/dial-in-conferencing.md) und "Verwalten von Konferenzrichtlinien in Skype for Business [Server".](../../manage/conferencing/conferencing-policies.md)  

## <a name="support-for-enterprise-and-anonymous-users"></a>Unterstützung für Unternehmensbenutzer und anonyme Benutzer

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Unternehmensbenutzer verfügen über Active Directory Domain Services-Anmeldeinformationen und Skype for Business Server-Konten innerhalb ihrer Organisation. Anonyme Benutzer verfügen nicht über Anmeldeinformationen innerhalb Ihrer Organisation. Im Kontext von Einwahlkonferenzen wird ein Benutzer in der Organisation eines Verbundpartners, der das PSTN verwendet, um eine Verbindung mit einer Konferenz herzustellen, wie ein anonymer Benutzer behandelt. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.
  
Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. Der Front-End-Server verwendet die Kombination aus vollständiger Telefonnummer oder Durchwahl und PIN, um Unternehmensbenutzer eindeutig ihren Active Directory-Anmeldeinformationen zu zuordnungen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.
  
> [!NOTE]
> Unternehmensbenutzer, die sich über ein Office-IP-Telefon oder über die Skype for Business Server Attendant einwählen, werden nicht zur Eingabe ihrer Telefonnummer aufgefordert, da sie bereits authentifiziert sind. 
  
Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.
  
> [!NOTE]
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt. 
  
Beim Planen einer Besprechung kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem er die Besprechung geschlossen oder gesperrt macht. In diesem Fall werden Einwahlbenutzer zur Authentifizierung aufgefordert. 
  
- Wenn Einwahlbenutzer fehlschlagen oder sich nicht authentifizieren, werden sie in die Lobby übertragen, wo sie bis ein Leiter sie annimmt oder ablehnt, oder es kommt zu einer Zeit, und die Verbindung wird getrennt.
    
- Nachdem sie für eine Konferenz zugelassen wurden, können Einwahlbenutzer am Audioteil der Konferenz teilnehmen und Überwahlbefehle (Dual-Tone Multi-Frequency, MEHRFREQUENZ) über die Telefontaste ausführen.
    
- Einwahlleiter können dtmF-Befehle ausführen, um die Möglichkeit der Teilnehmer zu deaktivieren, die Stummschaltung auf- oder zu deaktivieren, die Konferenz zu sperren oder zu entsperren, Personen aus der Lobby zu lassen und Ankündigungen zum Ein- und Ausstieg ein- oder auszuschalten.
    
- Führungskräfte können auch einen DTMF-Befehl verwenden, um alle Personen aus der Lobby zu erlauben, wodurch die Berechtigungen der Besprechung so geändert werden, dass jeder, der anschließend beitritt, teilnehmen kann. 
    
- Alle Einwahlteilnehmer können dtmF-Befehle ausführen, um Hilfe zu hören, die Konferenzliste anzuhören und sich selbst stummschalten zu lassen.
    
- Einwahlteilnehmer (d. h. unabhängig davon, ob sie sich über das Festnetz einwählen) hören während der Konferenz persönliche Ansagen, z. B. ob sie stumm geschaltet oder stumm geschaltet wurden, ob die Besprechung aufgezeichnet wird oder ob jemand in der Lobby wartet.
    
    > [!NOTE]
    > Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben. 
  

