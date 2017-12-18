---
title: "Was sind Telefonsystem Telefonzentralen?"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
description: "Learn what Phone System (Cloud PBX) auto attendents are and how to use them. "
---

# Was sind Telefonsystem Telefonzentralen?

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Telefonsystem in Office 365-Telefonzentralen verwendet werden können, um ein Menüsystem für Ihre Organisation zu erstellen, können internen und externen Anrufer, Menü System suchen und platzieren oder übertragen Anrufe an Benutzer Unternehmen oder Abteilungen in Ihrer Organisation verschieben.
  
Wenn Personen anrufen, werden sie mit einer Reihe von VoIP-Anweisungen angezeigt, mit die Hilfe sie tätigen eines Anrufs an einen Benutzer oder eine andere Person in Ihrer Organisation suchen und dann tätigen eines Anrufs an die Benutzer. Eine automatische Telefonzentrale ist eine Reihe von VoIP-Anweisungen oder und Audiodatei, die Anrufer anstelle einer personenbezogenen Operator zu hören, wenn sie in einer Organisation anrufen. Einer automatischen Telefonzentrale können Anrufer im Menü System verschieben, Anrufe, oder suchen Sie Benutzer mithilfe einer Zehnertastatur Telefon (MFV) oder Voicemail Eingaben mit der Spracherkennung. Einrichten einer automatischen Telefonzentrale für das Telefonsystem in Office 365 wechseln [Einrichten einer automatischen Telefonzentrale für Telefonsystem](set-up-a-phone-system-auto-attendant.md).
  
Eine Telefonsystem automatische Telefonzentrale weist die folgenden Features:
  
- Sie kann Unternehmensbegrüßungen oder informative Begrüßungen bereitstellen.
    
- Sie kann benutzerdefinierte Unternehmensmenüs bereitstellen. Diese Menüs können Sie so anpassen, dass sie aus mehreren Ebenen bestehen.
    
- Sie stellt eine Verzeichnissuche bereit, mit der Anrufer das Verzeichnis der Organisation nach einem Namen durchsuchen können.
    
- Anrufe können mit Personen in Ihrer Organisation sprechen oder eine Nachricht hinterlassen.
    
So richten Sie eine Telefonsystem automatische Telefonzentrale, wechseln Sie [Einrichten einer automatischen Telefonzentrale für Telefonsystem](set-up-a-phone-system-auto-attendant.md)ein.
  
## Erste Schritte

Die folgenden Punkte sind bei Ihrem Einstieg in die Verwendung von automatischen Telefonzentralen wichtig:
  
- Ihre Organisation muss eine Lizenz für Enterprise E3 plus **Telefonsystem** oder eine Lizenz für Enterprise E5 (mindestens) verfügen. Die Anzahl der **Telefonsystem** Benutzerlizenzen, die zugewiesen werden Nachteile, dass die Anzahl der Dienst, die Zahlen stehen für Telefonzentralen verwendet werden soll. Die Nummern der automatischen Telefonzentralen, die Sie haben, können, hängt von der Zahlen **Telefonsystem** und **Audio Konferenzen** Lizenzen, die in Ihrer Organisation zugewiesen werden. Weitere Informationen zur Lizenzierung, wechseln Sie[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
    > [!TIP]
    > Um umzuleiten Anrufe an einen Operator oder eine Menüoption, die eine Online-Benutzer mit einer Lizenz **Telefonsystem** ist, müssen Sie für Enterprise-VoIP zu aktivieren oder zu zuweisen Pläne aufrufen. Finden Sie unter[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). Sie können auch Windows PowerShell verwenden. Führen Sie zum Beispiel:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`
  
- Zum Abrufen und gebührenfreie Service Zahlen für Ihre Telefonzentralen verwenden, müssen Sie Kommunikation Gutschriften einrichten. Hierzu finden Sie [Was ist Guthaben für Kommunikationen?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md) und[Einrichten von Guthaben für Kommunikationen für Ihre Organisation](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).
    
    > [!IMPORTANT]
    > Telefonnummern von Benutzern (Abonnenten) können automatischen Telefonzentralen nicht zugewiesen werden - es können nur gebührenpflichtige oder gebührenfreie Telefonnummern verwendet werden. 
  
## Funktionsübersicht

### Namensanwahl

Wählen, indem Sie Namen ist ein Feature von einer automatischen Telefonzentrale, die als Verzeichnis durchsuchen bezeichnet wird. Sie können Personen, die der automatischen Telefonzentrale VoIP (Spracherkennung) oder deren Telefon Zehnertastatur (MFV) verwenden möchten, geben Sie einen Namen vollständigen oder teilweisen zu Verzeichnis des Unternehmens suchen, suchen Sie die Person aus, und lassen dann den Anruf übertragen zu einwählen. Wenn Sie über Skype für Business Online-Benutzer, **sind nicht erforderlich, dass eine Telefonnummer oder diese zugewiesen haben aufrufen Pläne verfügen müssen jedoch **Telefonsystem** Lizenz** für diese erreichbar ist bei der Suche mit Einwahlnummern anhand des Namens verfügen. Wählen, indem Sie Namen werden auch suchen, und stellen Sie Anrufe an Skype für Business Online-Benutzer, die in verschiedenen Ländern oder Regionen für internationale Organisationen gehostet werden können.
  
> [!CAUTION]
> Benutzer in lokalen Bereitstellungen von Skype for Business 2015 oder Lync Server 2013 und 2010 werden nicht aufgelistet, wenn jemand das Verzeichnis durchsucht. 
  
### Maximale Verzeichnisgröße

Es gibt keine Beschränkung für die Active Directory-Größe, die ein anhand des Namens wird unterstützt, wenn Sie dem Tastenfeld Telefon verwenden, für die Suche nach teilweisen oder vollständigen Namen (Vorname Nachname, und auch Nachname + Vorname) eingeben. Die maximale Größe von einer Liste der Name, die eine einzelnen Telefonzentrale unterstützen kann mithilfe von Namen Spracherkennung mit der Sprache, ist jedoch 80.000 Benutzer.
  
||||
|:-----|:-----|:-----|
|**Eingabetyp** <br/> |**Suchformat** <br/> |**Maximale Anzahl der Benutzer in einer Organisation** <br/> |
|MFV (Eingabe über die Wähltastatur)  <br/> |Teilweise  <br/> Vorname + Nachname  <br/> Nachname + Vorname  <br/> |Kein festes Limit  <br/> |
|Sprache (Spracheingabe)  <br/> |Vorname  <br/> Nachname  <br/> Vorname + Nachname  <br/> Nachname + Vorname  <br/> |80.000 Benutzer  <br/> |
   
> [!NOTE]
> Wenn Sie wählen, indem Sie Namen mit der Spracherkennung, aber Active Directory Ihres Unternehmens ist größer als 80.000 Benutzer verwenden und Sie noch nicht den Bereich Einwahlnummern zugänglich über den Namen mithilfe von Umfang bereitstellen, Einwahlnummern namentlich funktionieren weiterhin für Ihre Anrufer mithilfe einer Zehnertastatur Telefon und VoIP Eingaben für alle anderen Szenarien zur Verfügung. Der Umfang der Features können Sie die Namen beschränken, die durch Ändern des Suchbereichs Einwahlnummern namentlich für eine bestimmte automatische Telefonzentrale erreichbar sind. 
  
### Namensanwahl - Eingabe über die Wähltastatur (MFV)

Anrufer können Benutzer über die Namensanwahl erreichen, indem sie den vollständigen oder teilweisen Namen der gewünschten Person angeben. Das Gute daran ist, dass für die Eingabe des Namens verschiedene Formate verwendet werden können.
  
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
   
Bei der Suche nach Personen über die Wähltastatur eines Telefons können verschiedene Sonderzeichen verwendet werden. Die Anrufer werden beispielsweise aufgefordert, die Rautetaste (#) zu verwenden, während die Taste „0" (Null) für einen Leerschritt zwischen Namen verwendet wird. Wenn die Anrufer die Sterntaste (*) drücken, wird die Liste der übereinstimmenden Namen wiederholt.
  
|||
|:-----|:-----|
|**Sonderzeichen auf der Wähltastatur eines Telefons** <br/> |**Bedeutung** <br/> |
|# (Rautetaste)  <br/> |Endzeichen bei der Eingabe eines Namens  <br/> |
|0 (Null)  <br/> |Leerschritt zwischen Namen  <br/> |
|* (Sterntaste)  <br/> |Wiederholt die Liste der übereinstimmenden Namen.  <br/> |
   
### Namensanwahl - Namenserkennung mit Sprache

Anrufer können mithilfe von Sprache (Spracherkennung) nach Personen in Ihrer Organisation. suchen. Sie können jede in Active Directory in der Organisation enthaltene Person finden, indem sie den jeweiligen Namen sagen. Mithilfe von Spracheingabe können die Namen gesuchter Personen in verschiedenen Formaten erkannt werden, beispielsweise „Vorname", „Nachname", „Vorname + Nachname" oder „Nachname + Vorname".
  
Wenn Sie die Spracherkennung für eine automatische Telefonzentrale aktivieren, wird die Eingabe über die Wähltastatur eines Telefons (MFV) nicht deaktiviert, das heißt, beide Eingabetypen können verwendet werden. Die Eingabe über die Wähltastatur eines Telefons kann nicht deaktiviert werden und kann immer verwendet werden, auch wenn in der automatischen Telefonzentrale die Spracherkennung aktiviert ist.
  
Wie bei der Eingabe über die Wähltastatur eines Telefons wird den Anrufern, wenn mehrere Namen gefunden werden, eine Liste mit Namen zur Auswahl präsentiert.
  
Die Anrufer können Namen in den folgenden Formaten sagen:
  
|||||
|:-----|:-----|:-----|:-----|
|**Name mit Sprache** <br/> |**Suchtyp** <br/> |**Beispiel** <br/> |**Suchergebnis** <br/> |
|Vorname + Nachname  <br/> |Vollständig  <br/> |Amos Marble  <br/> |Amos Marble  <br/> |
|Nachname + Vorname  <br/> |Vollständig  <br/> |Marble Amos  <br/> |Amos Marble  <br/> |
|Vorname  <br/> |Vollständig  <br/> |Amos  <br/> |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Amos Jones.  <br/> |
|Nachname  <br/> |Vollständig  <br/> |Marble  <br/> |Drücken oder sagen Sie „1" für Amos Marble.  <br/> Drücken oder sagen Sie „2" für Ben Marble.  <br/> |
   
> [!NOTE]
> Es kann bis zu 36 Stunden für einen neuen Benutzer können Sie deren Namen im Verzeichnis aufgelistet wird, wenn eine Person wählen verwendet anhand des Namens mit der Spracherkennung dauern. 
  
### Sprachunterstützung

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
   
Die folgenden Sprachbefehle sind in den vierzehn (14﻿) für Spracherkennung unterstützten Sprachen verfügbar:
  
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
   
### Verwenden der Vermittlungsoption

Bei der Verwendung der Vermittlung für eine automatische Telefonzentrale handelt es sich um eine optionale Einstellung, mit der die Anrufer die Möglichkeit haben, mit einer echten Person zu sprechen.
  
Die Taste „0" und der Sprachbefehl „Vermittlung" (in allen für Spracherkennung unterstützten Sprachen) sind standardmäßig der Vermittlung zugewiesen.
  
> [!NOTE]
> Sie können die für die **Vermittlung** zu drückende Taste unter **Menüoptionen** auf eine andere Taste festlegen.
  
Als Vermittlung können Sie Folgendes festlegen:
  
- Ein Skype für Business Online-Benutzer, die eine **Telefonsystem**-Lizenz verfügt, die Enterprise-VoIP aktiviert oder anrufen Pläne, die Ihnen zugewiesen wurde. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Vertraut sind, wählen Sie eine **Person in Ihrem Unternehmen**, und legen Sie diese Person Anrufe automatisch an die Voicemail weitergeleitet werden.
    
    > [!NOTE]
    > Lokal mit Skype for Business Server 2015 oder Lync Server 2013 und 2010 gehostete Benutzer können nicht als Vermittlung verwendet werden. 
  
- Eine andere für Ihre Organisation eingerichtete automatische Telefonzentrale
    
- Eine beliebige in Ihrer Organisation eingerichtete Anrufwarteschleife. Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Erstellen einer Telefonsystem Anruf Warteschlange](create-a-phone-system-call-queue.md).
    
### Geschäftszeiten und Anrufbehandlung

Die Geschäftszeiten werden für jede einzelne automatische Telefonzentrale festgelegt. Wenn keine Geschäftszeiten festgelegt sind, gelten alle Tage und alle Tageszeiten als Geschäftszeiten, da standardmäßig ein 24/7-Zeitplan festgelegt ist. Die Geschäftszeiten können mit Pausen im Tagesverlauf festgelegt werden. Alle Zeiten, die nicht als Geschäftszeiten festgelegt sind, gelten als außerhalb der Geschäftszeiten liegend. Sie können verschiedene Optionen für die Behandlung eingehender Anrufe und verschiedene Begrüßungen (optional) festlegen. Beide können für Geschäftszeiten und für Zeiten außerhalb der Geschäftszeiten festgelegt werden.
  
Jede automatische Telefonzentrale verfügt über Anrufbehandlungsoptionen, die festgelegt werden können:
  
- Sie können festlegen, dass ein Anruf direkt nach der Begrüßung getrennt wird.
    
- Sie können auch folgende Aktionen ausführen:
    
  - Leiten Sie den Anruf an eine Skype für Business Online-Benutzer, die über eine Lizenz **Telefonsystem** verfügt, für die Enterprise-VoIP aktiviert ist, oder hat ihnen zugeordneten Pläne aufrufen. Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Vertraut sind, wählen Sie eine **Person in Ihrem Unternehmen**, und legen Sie diese Person Anrufe automatisch an die Voicemail weitergeleitet werden.
    
    > [!NOTE]
    > Lokal mit Skype for Business Server 2015 oder Lync Server 2013 und 2010 gehostete Benutzer werden nicht unterstützt. 
  
  - Den Anruf an eine Anrufwarteschleife umleiten. Weitere Informationen zu Anrufwarteschleifen finden Sie unter [Erstellen einer Telefonsystem Anruf Warteschlange](create-a-phone-system-call-queue.md).
    
  - Den Anruf an eine andere automatische Telefonzentrale umleiten, die Sie eingerichtet haben.
    
- Menüoptionen erstellen und eine Menüansage für die Anrufer wiedergeben. Beispiel: „Drücken Sie ‚1' für den Vertrieb oder ‚2' für den Service. Durch Drücken von ‚0' können Sie jederzeit mit der Vermittlung sprechen."
    
### Menüoptionen

Telefon System Telefonzentralen können Sie im Menü Anweisungen ("drücken Sie 1 für den Vertrieb, 2 für Dienste drücken") erstellen und Einrichten von Menüoptionen Routing Anrufe basierend auf der Auswahl des Benutzers. Einrichten von Menüoptionen für eine automatische Telefonzentrale ermöglicht eine Organisation, um die Person, die an ihr Ziel schneller, zu erhalten, unabhängig von einer personenbezogenen Operator eingehende Anrufe verarbeitet interaktiven Hilfestellung. Menü Anweisungen können erstellt werden, mit der Sprachausgabe (System generierten eingabeaufforderungen) oder durch Hochladen einer Audiodatei, die aufgezeichnet wurden. Spracherkennung VoIP-Befehle für Headset Navigation verwendet, aber das Anrufen von Personen können auch mithilfe der Tastatur Telefon Menüs navigieren.
  
Die Tasten „0" bis „9" können über das Skype for Business Admin Center den **Menüoptionen** in einer automatischen Telefonzentrale zugewiesen werden. Sie können unterschiedliche Menüoptionen für die Geschäftszeiten und für Zeiten außerhalb der Geschäftszeiten festlegen. Außerdem können Sie die Namensanwahl in den **Menüoptionen** aktivieren oder deaktivieren. Tasten können zugeordnet werden, um Anrufe an folgende Ziele durchzustellen:
  
- Eine Vermittlung, die standardmäßig der Taste „0" zugeordnet ist. Sie kann jedoch auch stattdessen einer beliebigen anderen Taste zugewiesen werden, oder die Vermittlung kann aus dem Menü entfernt werden.
    
- Anruf Warteschlange.
    
- Eine andere automatische Telefonzentrale. Sie können Menüs mit mehreren Ebenen einrichten, indem Sie eine **Menüoption** in einer automatischen Telefonzentrale auf eine andere automatische Telefonzentrale mit eigenen Menüoptionen verweisen lassen. Diese Telefonzentrale wird als „geschachtelte" automatische Telefonzentrale bezeichnet.
    
- Ein Skype für Business Online-Benutzer, die eine **Telefonsystem**-Lizenz verfügt, die Enterprise-VoIP aktiviert oder Pläne aufrufen weist, ihnen zugewiesenen... Sie können es einrichten, sodass die Person, die Aufrufen an die Voicemail gesendet werden kann. Vertraut sind, wählen Sie eine **Person in Ihrem Unternehmen**, und legen Sie diese Person Anrufe automatisch an die Voicemail weitergeleitet.
    
    > [!NOTE]
    > Lokal mit Skype for Business Server 2015 oder Lync Server 2013 und 2010 gehostete Benutzer können nicht in **Menüoptionen** verwendet werden.
  
Wenn die Spracherkennung aktiviert ist, werden die Namen aller Menüoptionen zu Stichwörtern für die Spracherkennung. So können Anrufer zum Beispiel „Eins" sagen, um die Menüoption auszuwählen, die der Taste „1" zugeordnet ist, oder sie können einfach „Vertrieb" sagen, um die Menüoption „Vertrieb" auszuwählen.
  
Informationen zum Einrichten einer automatischen Telefonzentrale finden Sie [Einrichten einer automatischen Telefonzentrale für Telefonsystem](set-up-a-phone-system-auto-attendant.md).
  
### Beziehen von Servicenummern für eine automatische Telefonzentrale

Bevor Sie Ihre automatischen Telefonzentralen erstellen und einrichten können, müssen Sie sich gebührenpflichtige oder gebührenfreie Servicenummern besorgen oder entsprechende vorhandene Nummern übertragen. Wenn Sie die gebührenpflichtigen oder gebührenfreien Servicenummern haben, werden diese im **Skype for Business Admin Center** unter **VoIP** auf der Registerkarte **Telefonnummern** angezeigt, und als **Nummerntyp** ist **Service - gebührenfrei** angegeben. Wie Sie Ihre Servicenummern erhalten, erfahren Sie unter[Abrufen von Skype for Business-Leistungsnummern](getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md). Wenn Sie eine vorhandene Servicenummer übertragen möchten, lesen Sie [Übertragen von Telefonnummern zu Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> Wenn Sie sich außerhalb der USA befinden, können Sie Servicenummern nicht über das Skype for Business Admin Center beziehen. Lesen Sie stattdessen [Verwalten von Telefonnummern für Ihre Organisation](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) nach, wie Sie außerhalb der USA vorgehen müssen.
  
## Ändern des Benutzers Anrufer-ID, um einen Anruf-Warteschlange Telefonnummer werden

Sie können Identität des Benutzers ändern ihre Anrufer-ID für ausgehende Anrufe an eine Warteschlange Anruf stattdessen durch Erstellen einer Richtlinie mithilfe des Cmdlets **New-CallingLineIdentity** schützen.
  
In dieser Instanz gehen Sie wie folgt:
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

Wenden Sie die Richtlinie für den Benutzer mithilfe des Cmdlets **Grant-CallingLineIdentity**. In dieser Instanz gehen Sie wie folgt:
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

Sie erhalten weitere Informationen zum Anrufer-ID-Einstellungen in Ihrer Organisation ändern [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).
  
## Verwandte Themen

[Hier ist das Ergebnis mit Telefonsystem in Office 365](here-s-what-you-get-with-phone-system-in-office-365.md)
  
[Einrichten von Anrufplänen](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

