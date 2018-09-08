---
title: Was sind automatische Telefonzentralen für das Telefonsystem?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Enthält Informationen zu automatischen Telefonzentralen Telefonsystem (Cloud, PBX) und deren Verwendung. '
ms.openlocfilehash: f37bed2629926154c037ec8dbaf5e61e9b9ec8d2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889933"
---
# <a name="what-are-phone-system-auto-attendants"></a>Was sind automatische Telefonzentralen für das Telefonsystem?

Telefonsystem in Office 365-Telefonzentralen verwendet werden können, um ein Menüsystem für Ihre Organisation zu erstellen, externe und interne Anrufer können, über ein Menüsystem platzieren, und durchstellen von Anrufen an Unternehmen Benutzer oder Abteilungen in Ihrer Organisation verschieben.
  
Anrufer hören eine Reihe von Sprachanweisungen, die ihnen dabei helfen, einen Benutzer anzurufen oder jemanden in Ihrer Organisation zu finden und diese Person dann anzurufen. Eine automatische Telefonzentrale ist eine Reihe von Ansagen oder einer Audiodatei, die anstelle einer human Operator Anrufer hören, wenn sie zu einer Organisation anrufen. Bei einer automatischen Telefonzentrale können die Anrufer durch das Menüsystem navigieren, Anrufe einleiten oder Benutzer suchen, indem sie eine Wähltastatur eines Telefons (MFV) oder Spracheingaben mit Spracherkennung verwenden. 
  
Um eine automatische Telefonzentrale für das Telefonsystem in Office 365 einzurichten, gehen Sie [Richten Sie eine automatische Telefonzentrale Telefonsystem](/skypeforbusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
Eine automatische Telefonzentrale Telefonsystem weist die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
    
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
    
- Es bietet Verzeichnissuche finden, die die Personen, die ermöglicht in aufrufen, um im Verzeichnis der Organisation für einen Namen zu suchen.
    
- Sie können einer Person, die Anrufe in erreichen, oder lassen Sie eine Nachricht für eine Person in Ihrer Organisation.
    
## <a name="getting-started"></a>Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:
  
- Ihre Organisation muss eine Lizenz Enterprise E3 plus **Telefonsystem** oder einer E5 Enterprise-Lizenz (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die Einfluss auf die Anzahl der Dienst Zahlen zugewiesen sind stehen für automatische Telefonzentralen verwendet werden soll. Die Anzahl der automatischen Telefonzentralen können Ihnen ist abhängig von der Zahlen **Telefonsystem** und **Audiokonferenzen** -Lizenzen, die in Ihrer Organisation zugewiesen sind. Weitere Informationen zur Lizenzierung finden Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
    > [!TIP]
    > Zum Umleiten von Anrufen an einen Operator oder eine Menüoption, die ein Benutzer Online mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder zu diesen zuweisen plant aufrufen. Weitere Informationen finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). Sie können auch die Windows PowerShell verwenden. Führen Sie beispielsweise folgenden Befehl aus:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Zum Abrufen und gebührenfreie Service Zahlen für die automatische Telefonzentralen verwenden, müssen Sie Communications haben einrichten. Hierzu finden Sie unter [Was sind Communications haben?](what-are-communications-credits.md) und [Communications haben für Ihre Organisation einrichten](set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
## <a name="feature-overview"></a>Funktionsübersicht

### <a name="dial-by-name"></a>Namensanwahl

Die Namensanwahl ist eine Funktion einer automatischen Telefonzentrale, die auch als Verzeichnissuche bekannt ist. Sie können die Personen, die an die automatische Telefonzentrale mit VoIP (Spracherkennung) oder ihre Telefontastatur (MFV) geben einen vollständigen oder teilweisen Namen Unternehmensverzeichnis suchen, suchen die Person, und klicken Sie dann der Anruf weitergeleitet werden. Wenn Sie über Skype für Business Online-Benutzer **sind nicht erforderlich, um eine Rufnummer verfügen oder haben aufrufen plant zugewiesen werden, jedoch über ein Telefon-Lizenz verfügen** , um eine erreichbar sein, bei der Suche mit Dial nach Namen verfügen. Dial namentlich werden auch ermitteln und durchstellen von Anrufen an Skype für Business Online Benutzer, die in verschiedenen Ländern oder Regionen für multinationale Unternehmen gehostet werden.
  
> [!CAUTION]
> Lokale Bereitstellung von Lync Server 2010-Benutzern wird nicht in das Verzeichnis Wenn jemand sie sucht aufgeführt. 
  
### <a name="maximum-directory-size"></a>Maximale Verzeichnisgröße

Es gibt keine Beschränkung für die Active Directory-Größe für die Einwahl namentlich unterstützt wird, wenn die Telefontastatur suchen zur Eingabe von teilweiser oder vollständiger Names (Vorname Nachname, und auch LastName + FirstName). Es ist jedoch die maximale Listengröße, dass eine einzelne automatische Telefonzentrale unterstützen kann Speech Recognition Namen mit 80.000 Benutzern.
  
||||
|:-----|:-----|:-----|
|**Eingabetyp** <br/> |**Suchformat** <br/> |**Maximale Anzahl der Benutzer in einer Organisation** <br/> |
|MFV (Eingabe über die Wähltastatur)  <br/> |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname  <br/> |Kein festes Limit  <br/> |
|Sprache (Spracheingabe)  <br/> |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  <br/> |80.000 Benutzern  <br/> |
   
> [!NOTE]
> Bei Verwendung der Einwahl namentlich mit Speech Recognition, aber Ihre Organisation Active Directory ist größer als 80.000 Benutzern und Sie noch nicht den Bereich der Einwahl über den Namen mithilfe von DFÜ-bereichsfeature begrenzt, Dial namentlich funktioniert auch weiterhin für die über die Tastatur eine Rufnummer für Anrufer , und Spracheingaben werden für alle anderen Szenarien zur Verfügung gestellt. DFÜ-bereichsfeature können Sie die Namen einzuschränken, die durch eine Änderung der Zugriffsnummer für eine bestimmte automatische Telefonzentrale namentlich erreichbar sind. 
  
### <a name="dial-by-name---keypad-dtmf-entry"></a>Namensanwahl - Eingabe über die Wähltastatur (MFV)

Personen einwählen, können Dial namentlich erreichen von Benutzern durch Angeben von entweder den vollständigen oder teilweisen Namen der Person, die sie erreichen möchten. Das gute ist, dass es sind verschiedene Formate, die verwendet werden können, wenn der Name eingegeben wurde.
  
Die Benutzer können bei der Suche im Verzeichnis Ihrer Organisation mit der Taste „0" (Null) einen Leerschritt zwischen dem Vornamen und dem Nachnamen oder dem Nachnamen und dem Vornamen eingeben. Bei der Eingabe des Namens werden sie aufgefordert, die Eingabe über die Wähltastatur mit der Rautetaste (#) zu beenden. Beispiel: „Drücken Sie nach dem Namen der gewünschten Person die Rautetaste." Wenn mehrere Namen gefunden werden, wird den Anrufern eine Liste mit Namen zur Auswahl präsentiert.
  
Anrufer können bei der Suche nach Namen in Ihrer Organisation über die Wähltastatur eines Telefons die folgenden Suchformate verwenden:
  
|||||
|:-----|:-----|:-----|:-----|
|**Namensformat** <br/> |**Suchtyp** <br/> |**Beispiel** <br/> |**Suchergebnis** <br/> |
|Vorname + Nachname  <br/> |Vollständig  <br/> |Amos0Marble#  <br/> |Amos Marble  <br/> |
|Nachname + Vorname  <br/> |Vollständig  <br/> |Marble0Amos#  <br/> |Amos Marble  <br/> |
|Vorname  <br/> |Vollständig  <br/> |Amos#  <br/> |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus.  <br/> |
|Nachname  <br/> |Vollständig  <br/> |Marble#  <br/> |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Mary Marble.  <br/> |
|Vorname oder Nachname  <br/> |Teilweise  <br/> |Mar#  <br/> |Drücken Sie „1" für Mary Marble.  <br/> Drücken Sie „2" für Mary Jones.  <br/> Drücken Sie „3" für Amos Marcus.  <br/> |
|Vorname + Nachname  <br/> |Teilweise  <br/> |Mar0Amos#  <br/> |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus.  <br/> |
|Nachname + Vorname  <br/> |Teilweise  <br/> |Mar0Am#  <br/> |Drücken Sie „1" für Amos Marble.  <br/> Drücken Sie „2" für Amos Marcus.  <br/> |
   
Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Beispielsweise die Person gebeten, verwenden Sie die Rautetaste (#), während für ein Leerzeichen zwischen Null (0)-Taste verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|||
|:-----|:-----|
|**Sonderzeichen auf der Wähltastatur eines Telefons** <br/> |**Bedeutung** <br/> |
|# (Rautetaste)  <br/> |Endzeichen bei der Eingabe eines Namens  <br/> |
|0 (Null)  <br/> |Leerschritt zwischen Namen  <br/> |
|* (Sterntaste)  <br/> |Wiederholt die Liste der übereinstimmenden Namen.  <br/> |
   
### <a name="dial-by-name---name-recognition-with-speech"></a>Namensanwahl - Namenserkennung mit Sprache

Personen können andere Personen in ihrer Organisation über ihre VoIP (Spracherkennung) suchen. Sie können auch erreichen alle in Active Directory des Unternehmens sagen Sie den Namen der Person, die sie suchen möchten. Mithilfe von Spracheingaben erkennen Namen in verschiedenen Formaten, einschließlich FirstName, LastName, FirstName LastName, oder LastName + FirstName.
  
Wenn Sie die Spracherkennung für eine automatische Telefonzentrale aktivieren, werden nicht Telefon Tastatur Eintrag (MFV) deaktiviert werden, damit beide Arten von Eingabe verwendet werden können. Telefon Tastatur Eintrag kann nicht deaktiviert werden und kann jederzeit verwendet werden, selbst wenn die Spracherkennung für die automatische Telefonzentrale aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons wird den Anrufern, wenn mehrere Namen gefunden werden, eine Liste mit Namen zur Auswahl präsentiert.
  
Die Anrufer können Namen in den folgenden Formaten sagen:
  
|||||
|:-----|:-----|:-----|:-----|
|**Nennen Sie mit der Sprache** <br/> |**Suchtyp** <br/> |**Beispiel** <br/> |**Suchergebnis** <br/> |
|Vorname + Nachname  <br/> |Vollständig  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Nachname + Vorname  <br/> |Vollständig  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Vorname  <br/> |Vollständig  <br/> |Amos  <br/> |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones.  <br/> |
|Nachname  <br/> |Vollständig  <br/> |Marble  <br/> |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble.  <br/> |
   
> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer ihre Namen in das Verzeichnis mit Namen für die Spracherkennung für Einwahl aufgeführt haben dauern. 
  
### <a name="language-support"></a>Sprachunterstützung

Für Text-zu-Sprache sind die folgenden Sprachen verfügbar:
  
||||
|:-----|:-----|:-----|
|Arabisch (EG)  <br/> |Englisch (NZ)  <br/> |Koreanisch (KO)  <br/> |
|Chinesisch (HK)  <br/> |Englisch (Großbritannien)  <br/> |Norwegisch (NO)  <br/> |
|Chinesisch (TW)  <br/> |Englisch (USA)  <br/> |Polnisch (PL)  <br/> |
|Chinesisch (ZH)  <br/> |Finnisch (FI)  <br/> |Portugiesisch (BR)  <br/> |
|Dänisch (DA)  <br/> |Französisch (CA)  <br/> |Portugiesisch (PT)  <br/> |
|Niederländisch (NL)  <br/> |Französisch (FR)  <br/> |Russisch (RU)  <br/> |
|Englisch (AU)  <br/> |Deutsch (DE)  <br/> |Spanisch (ES)  <br/> |
|Englisch (CA)  <br/> |Italienisch (IT)  <br/> |Spanisch (MX)  <br/> |
|Englisch (IN)  <br/> |Japanisch (JP)  <br/> |Schwedisch (SV)  <br/> |
   
Spracherkennung für automatische Telefonzentralen ist in den folgenden Sprachen verfügbar:
  
|||
|:-----|:-----|
|Chinesisch (ZH)  <br/> |Französisch (FR)  <br/> |
|Englisch (AU)  <br/> |Deutsch (DE)  <br/> |
|Englisch (CA)  <br/> |Italienisch (IT)  <br/> |
|Englisch (IN)  <br/> |Japanisch (JP)  <br/> |
|Englisch (Großbritannien)  <br/> |Portugiesisch (BR)  <br/> |
|Englisch (USA)  <br/> |Spanisch (ES)  <br/> |
|Französisch (CA)  <br/> |Spanisch (MX)  <br/> |
   
Die folgenden Sprachbefehle sind in den vierzehn (14) für Spracherkennung unterstützten Sprachen verfügbar:
  
|||
|:-----|:-----|
|**Sprachbefehl** <br/> |**Bedeutung** <br/> |
|Ja  <br/> |Ja - entspricht dem Drücken von „1" für „Ja".  <br/> |
|Nein  <br/> |Nein - entspricht dem Drücken von „2" für „Nein".  <br/> |
|Wiederholen  <br/> |Wiederholt die Liste der Optionen - entspricht dem Drücken von „*" zum Wiederholen der Liste der Optionen.  <br/> |
|Vermittlung  <br/> |Zurück zur Vermittlung - entspricht dem Drücken von „0" für „Vermittlung".  <br/> |
|Hauptmenü  <br/> |Die Anrufer gelangen zum Hauptmenü der automatischen Telefonzentrale.  <br/> |
|Null  <br/> |Entspricht dem Drücken von „0" (standardmäßig identisch mit „Vermittlung").  <br/> |
|Eins  <br/> |Entspricht dem Drücken von „1".  <br/> |
|Zwei  <br/> |Entspricht dem Drücken von „2".  <br/> |
|Drei  <br/> |Entspricht dem Drücken von „3".  <br/> |
|Vier  <br/> |Entspricht dem Drücken von „4".  <br/> |
|Fünf  <br/> |Entspricht dem Drücken von „5".  <br/> |
|Sechs  <br/> |Entspricht dem Drücken von „6".  <br/> |
|Sieben  <br/> |Entspricht dem Drücken von „7".  <br/> |
|Acht  <br/> |Entspricht dem Drücken von „8".  <br/> |
|Neun  <br/> |Entspricht dem Drücken von „9".  <br/> |
   
### <a name="using-the-operator-option"></a>Verwenden der Vermittlungsoption

Bei der Verwendung der Vermittlung für eine automatische Telefonzentrale handelt es sich um eine optionale Einstellung, mit der die Anrufer die Möglichkeit haben, mit einer echten Person zu sprechen.
  
Die Taste „0" und der Sprachbefehl „Vermittlung" (in allen für Spracherkennung unterstützten Sprachen) sind standardmäßig der Vermittlung zugewiesen.
  
> [!NOTE]
> Sie können die Schaltfläche festlegen, die für den **Operator** mit **Menüoptionen**auf einen anderen Schlüssel abgelegt wird. 
  
Als Vermittlung können Sie Folgendes festlegen:
  
- Eine Skype für Business Online Benutzer mit einem **Telefonsystem** lizenzieren, die Enterprise-VoIP aktiviert oder hat aufrufen plant zugeordnet ist, diese. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
    
    > [!NOTE]
    > Benutzer gehostet: lokal mit Lync Server 2010 kann nicht als Operator verwendet werden. 
  
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
    
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zum Anruf Warteschlangen finden Sie unter [Erstellen einer Telefonsystem Anruf Warteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
### <a name="business-hours-and-call-handling"></a>Geschäftszeiten und Anrufbehandlung

Geschäftszeiten werden für jede automatische Telefonzentrale festgelegt. Wenn Geschäftszeiten festgelegt sind, werden alle Tage und alle Stunden am Tag Geschäftszeiten berücksichtigt, da standardmäßig ein Zeitplan 24/7 festgelegt ist. Geschäftszeiten kann mit Breaks rechtzeitig während der Tag und alle der Stunden, die nicht festgelegt werden, wie Geschäftszeiten Geschäftszeiten gelten festgelegt werden. Sie können unterschiedliche eingehende Anrufbehandlung Optionen und anderen Ansage (die optionale sind), und beide für Geschäftszeiten und Geschäftszeiten festgelegt sein.
  
Jede automatische Telefonzentrale hat Anrufbehandlung Optionen, die festgelegt werden können:
  
- Sie können festlegen, dass ein Anruf direkt nach der Begrüßung getrennt wird.
    
- Sie können auch folgende Aktionen ausführen:
    
  - Leiten den Anruf an einen Skype für Business Online-Benutzer, der über eine Lizenz **Telefonsystem** verfügt, die Enterprise-VoIP aktiviert ist, oder sie zugewiesen wurde plant aufrufen. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
    
    > [!NOTE]
    > Benutzer gehostet: lokal mit Lync Server 2010 werden nicht unterstützt. 
  
  - Umleiten des Anrufs an eine Warteschleife Anruf. Weitere Informationen zum Anruf Warteschlangen finden Sie unter [Erstellen einer Telefonsystem Anruf Warteschleife](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).
    
  - Leiten Sie den Anruf an eine andere automatische Telefonzentrale, die Sie eingerichtet haben.
    
- Menüoptionen erstellen und eine Menüansage für die Anrufer wiedergeben. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."
    
### <a name="menu-options"></a>Menüoptionen

System-Telefonzentralen Phone können Sie Menüansagen ("drücken Sie 1 für den Vertrieb, 2 für Dienste drücken") erstellen und Einrichten von Menüoptionen für das Anrufrouting basierend auf der Auswahl des Benutzers. Durch Einrichten von Menüoptionen für eine automatische Telefonzentrale können Organisationen die Anrufer interaktiv schneller an ihr Ziel führen, ohne dass dazu Vermittlungsmitarbeiter für die Abwicklung der eingehenden Anrufe benötigt werden. Menüansagen können erstellt werden, mithilfe der Sprachausgabe (vom System generierte Ansagen) oder durch Hochladen einer Audiodatei, die aufgezeichnet wurden. Bei der Spracherkennung werden Sprachbefehle für Freisprechnavigation verwendet, aber die Anrufer können auch mithilfe der Wähltastatur eines Telefons in den Menüs navigieren.
  
Tasten 0 bis 9 können in eine automatische Telefonzentrale mit der Skype für Business Administrationscenter **Menüoptionen** zugewiesen werden. Verschiedene Sätze von Menüoptionen können erstellt werden, für die Geschäftszeiten und außerhalb der Geschäftszeiten, und Sie aktivieren oder deaktivieren Sie namentlich in den **Optionen im Menü**wählen können. Schlüssel können zum Weiterleiten der Anrufe für zugeordnet werden:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Jedoch möglich erneut zugewiesen an eine beliebige Taste, oder aus dem Menü entfernt.
    
- Eine Warteschlange Anruf.
    
- Eine andere automatische Telefonzentrale. Menüs mit mehreren Ebenen können eingerichtet werden, zeigen Sie eine **Menüoption** in eine automatische Telefonzentrale an eine andere automatische Telefonzentrale mit einem eigenen Satz von Menüoptionen, die eine "geschachtelte" Automatische Telefonzentrale bezeichnet wird.
    
- Eine Skype für Business Online Benutzer mit einem **Telefonsystem** lizenzieren, die Enterprise-VoIP aktiviert oder hat aufrufen plant zugeordnet ist, diese. Sie können einrichten, dass Anrufer an die Voicemail gesendet werden. Dazu wählen Sie eine **Person in Ihrem Unternehmen** aus, deren Anrufe dann automatisch direkt an die Voicemail weitergeleitet werden.
    
    > [!NOTE]
    > Benutzer gehostet: lokal mit Lync Server 2010 kann nicht im **Menüoptionen**verwendet werden. 
  
Der Name des jede Menüoption wird ein Spracherkennung Schlüsselwort, wenn die Spracherkennung aktiviert wurde. Beispielsweise können Anrufer sagen Sie "1", um die Menüoption, Schlüssel 1 zugeordnet sind, wählen oder sie können einfach sagen "Sales", um die gleichen Menüoption mit dem Namen "Sales".
  
Um eine automatische Telefonzentrale und den Menüoptionen einzurichten, gehen Sie [Richten Sie eine automatische Telefonzentrale Telefonsystem](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).
  
### <a name="getting-service-numbers-for-an-auto-attendant"></a>Beziehen von Servicenummern für eine automatische Telefonzentrale

Before you can create and set up your auto attendants, you will need to get or transfer your existing toll or toll-free service numbers. Nachdem Sie die gebührenpflichtige oder gebührenfreie Service Telefonnummern erhalten möchten, sie werden angezeigt, in der **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**und **Datentyp Zahl** aufgeführt wird als **-Dienst - gebührenfreie Rufnummer aufgeführt werden **. Um die Rufnummern Service erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen und die Microsoft-Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) oder für Übertragung und vorhandenen Service-Nummer, finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA sind, können der Skype für Business Administrationscenter Sie um Service Zahlen zu erhalten. Wechseln Sie [Telefonnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) stattdessen wie es angezeigt.
  
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a>Ändern der Anrufer-ID des Benutzers zu einer Rufnummer der Anrufwarteschleife

Sie können die Identität eines Benutzers schützen, indem Sie seine Anrufer-ID für ausgehende Anrufe zu einer Rufnummer der Warteschleife ändern. Dazu müssen Sie mit dem Cmdlet **New-CallingLineIdentity** eine Richtlinie erstellen.
  
Zu diesem Zweck führen Sie Folgendes aus:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mit dem Cmdlet **Grant-CallingLineIdentity** an. Zu diesem Zweck führen Sie Folgendes aus:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Sie erhalten weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation [kann Anrufer-ID werden Verwendung in Ihrer Organisation](/SkypeForBusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization)zu ändern.
  
## <a name="related-topics"></a>Verwandte Themen
[Das bekommen Sie mit Telefonsystem in Office 365](here-s-what-you-get-with-phone-system.md)

[Anfordern von Servicenummern für Skype for Business und Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 