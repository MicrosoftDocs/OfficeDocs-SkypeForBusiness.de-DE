---
title: Planen von Einwahlkonferenzen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Zusammenfassung: Lesen Sie dieses Thema, um mehr über die Planung von Einwahlkonferenzen in Skype for Business Server zu erfahren.'
---

# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Planen von Einwahlkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um mehr über die Planung von Einwahlkonferenzen in Skype for Business Server zu erfahren.
  
Einwahlkonferenzen sind ein optionales Feature von Skype for Business Server, mit dem Besprechungsteilnehmer am Audioteil einer Besprechung teilnehmen können, indem sie sich über ein Telefon in die Besprechung einwählen. Einwahlkonferenzen sind ein Teil von Audiokonferenzen und erfordern zusätzliche Konfiguration. In diesem Thema wird beschrieben, was Sie bedenken müssen, bevor Sie Einwahlkonferenzen für Ihre Organisation bereitstellen. 
  
Einige der für Einwahlkonferenzen erforderlichen Komponenten sind spezifisch für Einwahlkonferenzen, andere Enterprise-VoIP Komponenten. Obwohl Einwahlkonferenzen einige der gleichen Komponenten verwenden, die Enterprise-VoIP verwendet, können Sie Einwahlkonferenzen auch dann bereitstellen, wenn Sie Enterprise-VoIP nicht bereitstellen. In diesem Abschnitt werden die Komponenten beschrieben, die für Einwahlkonferenzen benötigt werden. Weitere Informationen zum Planen einer vollständigen Enterprise-VoIP Lösung finden Sie unter [Planen Ihrer Enterprise-VoIP Lösung in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
Einwahlkonferenzen erfordern, dass Sie eine Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) herstellen, indem Sie einen Vermittlungsserver bereitstellen. Zusätzlich zur Bereitstellung eines Vermittlungsservers müssen Sie Folgendes berücksichtigen, um Einwahlkonferenzen für Ihre Organisation zuzulassen:
  
- Ihr Plan für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN)
    
- Ihr Plan für Wählpläne, Zugriffsnummern und Konferenzregionen
    
- Ihr Plan zum Erstellen von Konferenzverzeichnissen
    
- Ihre Konferenzrichtlinie zum Zulassen des Einwahlzugriffs
    
- Unterstützung für Unternehmensbenutzer und anonyme Benutzer
    
> [!NOTE]
> Wenn Sie Einwahlkonferenzen bereitstellen, müssen Sie sie in jedem Pool bereitstellen, in dem Sie Skype for Business Server Konferenzen bereitstellen. Sie müssen keine Zugriffsnummern zuweisen – die Nummern, die Teilnehmer anrufen, um an einer Konferenz teilzunehmen – in jedem Pool, aber Sie müssen die Einwahlfunktion in jedem Pool bereitstellen. Diese Anforderung unterstützt das Feature für aufgezeichnete Namen, wenn ein Benutzer eine Zugriffsnummer aus einem Pool aufruft, um an einer Skype for Business Server Konferenz in einem anderen Pool teilzunehmen. 
  
## <a name="plan-for-pstn-connectivity"></a>Planen der PSTN-Konnektivität

Einwahlkonferenzen erfordern mindestens einen Vermittlungsserver und mindestens ein PSTN-Gateway (Public Switched Telephone Network). 
  
Sie können einen Vermittlungsserver an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem zentralen Standort können Sie einen Vermittlungsserver in einem Front-End-Pool oder Standard Edition Server oder auf einem eigenständigen Server oder Pool bereitstellen. An einem Zweigstellenstandort können Sie einen Vermittlungsserver auf einem eigenständigen Server oder als Komponente der Survivable Branch Appliance bereitstellen.
  
Sie können ein PSTN-Gateway an einem zentralen Standort oder an einem Zweigstellenstandort bereitstellen. An einem Zweigstellenstandort kann das PSTN-Gateway eigenständig oder eine Komponente der Survivable Branch Appliance sein.
  
Ausführliche Informationen zu den Anforderungen für Vermittlungsserver und PSTN-Gateways finden Sie unter ["Vermittlungsserverkomponente in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)[", "Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)" und ["Definieren eines Gateways im Topologie-Generator in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Planen von Wählplänen, Zugriffsnummern und Konferenzregionen

Zum Konfigurieren von Einwahlkonferenzen erstellen Sie Wählpläne und Zugriffsnummern für Einwahlkonferenzen. Außerdem geben Sie die Einwahlregionen an, die den Wählplänen eine Zugriffsnummer für Einwahlkonferenzen zuordnen. Das bedeutet im Detail:
  
- Wählpläne sind Sätze von Normalisierungsregeln, die die Nummer und das Muster von Ziffern in einer Telefonnummer angeben und die Telefonnummer in das standard E.164-Format übersetzen, das für die Anrufweiterleitung erforderlich ist.
    
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
    
- Regionen müssen unbedingt so benannt werden, dass sie klar erkennbar sind. Der Benutzer kann anhand der Regionsnamen die Region einer Besprechung ändern, damit in der Einladung andere Zugriffsnummern enthalten sind. (Wenn Benutzer Outlook zum Planen einer Besprechung verwenden, verwendet der Benutzer das Onlinebesprechungs-Add-In für Skype for Business, um die Region zu ändern).)
    
- Regionen sollten so konzipiert werden, dass jedem eingeladenen Benutzer, der sich in eine Konferenz einwählen möchte, eine lokale Zugriffsnummer in der Konferenzeinladung angezeigt wird.
    
- Mithilfe Skype for Business Server Verwaltungsshell-Cmdlets können Sie die Reihenfolge konfigurieren, in der Zugriffsnummern innerhalb einer Region auf der Seite "Einwahlkonferenzen" Einstellungen angezeigt werden (und somit die Reihenfolge, in der sie in der Konferenzseinladung angezeigt werden).
    
- Jeder Benutzer kann an jedem beliebigen Standort eine beliebige Einwahlnummer wählen, um an einer Konferenz teilzunehmen.
    
Weitere Informationen zum Erstellen eines Wählplans finden Sie unter [Erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) und [Erstellen oder Ändern einer Normalisierungsregel in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Planen von Konferenzverzeichnissen

Konferenzverzeichnisse verwalten eine Zuordnung zwischen der alphanumerischen Besprechungs-ID, die ein Teilnehmer für die Teilnahme an einer Konferenz verwendet, wenn er Skype for Business verwendet, und der rein numerischen Konferenz-ID, die ein Einwahlkonferenzteilnehmer für die Teilnahme an der Konferenz verwendet. Das Format der Konferenz-ID lautet folgendermaßen:
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


Indem mehrere Konferenzverzeichnisse erstellt werden, wird sichergestellt, dass Konferenz-IDs kurz bleiben, solange keine sehr große Anzahl Konferenzen erstellt wurde. Um etwa sechsstellige Konferenz-IDs zu erhalten, wird in einer Organisation mit einer typischen Konferenzanzahl pro Benutzer empfohlen, pro 999 Benutzer im Pool je ein Konferenzverzeichnis zu erstellen. Mit dieser Richtlinie können die Konferenz-IDs in der Regel klein gehalten werden. Sobald die Anzahl der Konferenzverzeichnisse (in den Pools) neun übersteigt, wird die Konferenz-ID-Nummer jedoch größer, um zusätzliche Konferenzen zu unterstützen.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Planen einer Konferenzrichtlinie, die den Einwahlzugriff ermöglicht

Konferenzen müssen für den Einwahlzugriff aktiviert sein, wenn Sie Konferenzrichtlinien konfigurieren. In der Standardeinstellung umfassen Konferenzen, die für den Zugriff per Einwahl aktiviert sind, die folgenden Informationen in der Konferenzeinladung:
  
- Eine numerische Konferenz-ID, die die Konferenz identifiziert
    
- Eine oder mehrere PSTN-Zugriffsnummern
    
- Ein Link zu einer Einstellungen Seite für Einwahlkonferenzen, die eine vollständige Liste der Zugriffsnummern mit den zugehörigen Sprachen, einen Ort zum Erstellen, Zurücksetzen oder Aufheben der Blockierung von persönlichen Identifikationsnummern (PINs) und andere Informationen wie DTMF-Steuerelemente (Dual-Tone Multi-Frequency) enthält
    
Weitere Informationen zu Konferenzrichtlinien finden Sie unter [Konfigurieren von Einwahlkonferenzen in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) und [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Unterstützung für Unternehmensbenutzer und anonyme Benutzer

Einwahlkonferenzen können sowohl für Unternehmensbenutzer als auch für anonyme Benutzer eingesetzt werden. Enterprise Benutzer über Active Directory Domain Services-Anmeldeinformationen und Skype for Business Server Konten innerhalb ihrer Organisation verfügen. Anonyme Benutzer verfügen nicht über Anmeldeinformationen innerhalb Ihrer Organisation. Im Kontext von Einwahlkonferenzen wird ein Benutzer in der Organisation eines Verbundpartners, der das PSTN zum Herstellen einer Verbindung mit einer Konferenz verwendet, wie ein anonymer Benutzer behandelt. Im Gegensatz zu anderen Kontexten werden Partnerbenutzer bei Einwahlkonferenzen nicht authentifiziert.
  
Unternehmensbenutzer oder Konferenzleiter, die einer für den Zugriff per Einwahl aktivierten Konferenz beitreten, wählen eine der Zugriffsnummern für die Konferenz und werden anschließend zur Eingabe der Konferenz-ID aufgefordert. Wenn der Konferenzleiter der Besprechung noch nicht beigetreten ist, können Benutzer entweder ihre Unified Communications-Durchwahl (UC) (oder die vollständige Telefonnummer) und PIN eingeben oder warten, bis der Konferenzleiter bestätigt, dass sie zur Konferenz zugelassen werden. Besprechungsorganisatoren können der Besprechung als Konferenzleiter beitreten, indem sie lediglich ihre PIN eingeben. Der Front-End-Server verwendet die Kombination aus vollständiger Telefonnummer oder Erweiterung und PIN, um Unternehmensbenutzer eindeutig ihren Active Directory-Anmeldeinformationen zuzuordnen. So werden Unternehmensbenutzer anhand ihres Namens in der Konferenz authentifiziert und identifiziert. Unternehmensbenutzer können auch eine Konferenzrolle übernehmen, die vom Organisator vorgegeben ist.
  
> [!NOTE]
> Enterprise Benutzer, die sich über ein Office-IP-Telefon oder über Skype for Business Server Telefonzentrale einwählen, werden nicht zur Eingabe ihrer Telefonnummer aufgefordert, da sie bereits authentifiziert sind. 
  
Anonyme Benutzer, die einer Einwahlkonferenz beitreten möchten, wählen eine der Zugriffsnummern für die Konferenz und werden zur Eingabe der Konferenz-ID aufgefordert. Nicht authentifizierte anonyme Benutzer werden zudem zur Aufzeichnung ihres Namens aufgefordert. Der aufgezeichnete Name identifiziert nicht authentifizierte Benutzer in der Konferenz. Anonyme Benutzer werden erst zur Konferenz zugelassen, wenn mindestens ein Konferenzleiter oder authentifizierter Benutzer beigetreten ist. Das Zuweisen einer vordefinierten Rolle zu anonymen Benutzern ist nicht möglich.
  
> [!NOTE]
> Unternehmensbenutzer, die ihre Telefonnummer und PIN nicht eingeben, werden nicht authentifiziert. Diese Benutzer werden zur Aufzeichnung ihres Namens aufgefordert und in der Konferenz als anonyme Benutzer behandelt. 
  
Beim Planen einer Besprechung kann der Besprechungsorganisator den Zugriff auf die Besprechung einschränken, indem er die Besprechung geschlossen oder gesperrt macht. In diesem Fall werden Einwahlbenutzer zur Authentifizierung aufgefordert. 
  
- Wenn Einwahlbenutzer nicht authentifiziert werden oder sich nicht authentifizieren möchten, werden sie in den Wartebereich versetzt, bis ein Leiter sie akzeptiert oder ablehnt, oder wenn ein Timeout auftritt und die Verbindung getrennt wird.
    
- Nachdem sie zu einer Konferenz zugelassen wurden, können Einwahlbenutzer am Audioteil der Konferenz teilnehmen und DTMF-Befehle (Dual-Tone Multi-Frequency) mithilfe der Wähltastatur des Telefons ausführen.
    
- Einwahlleiter können DTMF-Befehle ausführen, um die Möglichkeit der Teilnehmer zu aktivieren oder zu deaktivieren, die Konferenz zu sperren oder zu entsperren, Personen aus dem Wartebereich zuzulassen und Ankündigungen beim Ein- und Ausstieg ein- oder auszuschalten.
    
- Führungskräfte können auch einen DTMF-Befehl verwenden, um alle Personen aus dem Wartebereich zuzulassen, wodurch die Berechtigungen der Besprechung geändert werden, damit alle Personen teilnehmen können, die anschließend teilnehmen. 
    
- Alle Einwahlteilnehmer können DTMF-Befehle ausführen, um Hilfe zu hören, den Konferenzplan anzuhören und sich selbst stumm zu schalten.
    
- Einwahlteilnehmer (d. h. ob sie aus dem PSTN wählen) hören persönliche Ankündigungen während der Konferenz, z. B. ob sie stummgeschaltet oder nicht stumm geschaltet wurden, ob die Besprechung aufgezeichnet wird oder ob jemand im Wartebereich wartet.
    
    > [!NOTE]
    > Für Teilnehmer, die sich nicht einwählen, sondern der Besprechung über einen Link beitreten, werden keine persönlichen Ansagen wiedergegeben. 
  

