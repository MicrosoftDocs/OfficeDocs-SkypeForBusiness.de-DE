---
title: Testen Ihrer Skype for Business Online-Installation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 19873b1f-8f7e-4dd8-92f4-2ce11344ed5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn to save time, support calls and increase satisfaction by setting up test accounts and computers, and testing dial-in conferencing, online features such as person-to-person calls, conferencing, and sign in and out. '
ms.openlocfilehash: 94a167dad9ab745993315450717e7efc7c5e00bc
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="test-your-skype-for-business-online-installation"></a>Testen Ihrer Skype for Business Online-Installation

Sie können Zeit sparen, die Zahl der Supportanrufe reduzieren und die Akzeptanz seitens der Benutzer steigern, indem Sie Ihre Skype for Business Online-Installation testen, bevor Sie sie für jedermann in der Organisation einrichten.
  
Nachstehend die Voraussetzungen:
  
- Mindestens drei Office 365-Konten (Ihres und mindestens zwei weitere Konten)
    
- Computer zum Testen der einzelnen Konten. Richten Sie die Computer so ein, wie ein normaler Computer in Ihrer Organisation eingerichtet würde.
    
- Ein Konto bei einem Audiokonferenzanbieter für Skype for Business Online. Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).
    
## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun?

> [Einrichten von Testkonten](test-your-skype-for-business-online-installation.md#__toc328126910)
    
> [Einrichten von Testcomputern](test-your-skype-for-business-online-installation.md#__toc328126911)
    
> [Einrichten von Audiokonferenzen](test-your-skype-for-business-online-installation.md#__toc328126912)
    
> [Testen der Funktionen und Geräte von Skype for Business Online](test-your-skype-for-business-online-installation.md#__toc328126913)
    
## <a name="set-up-test-accounts"></a>Einrichten von Testkonten
<a name="__toc328126910"> </a>

1. Wechseln Sie zu **Administrator** > **Office 365** > **Benutzer und Gruppen**, wählen Sie anschließend „Hinzufügen"![Hinzufügen](../images/328ffb57-5f31-430a-b653-4a6b8e76d338.png) aus und geben Sie die erforderlichen Informationen ein.
    
2. Wenn Sie zu Schritt 4 (E-Mail) gelangen, geben Sie Ihre eigene E-Mail-Adresse ein. Sie besitzen dann einen Eintrag für den Namen und das Kennwort des neuen Benutzers. 
    
3. Wiederholen Sie die Schritte 1 und 2, bis Sie die Anzahl der gewünschten Testkonten erstellt haben. Zum Testen der Onlinebesprechungsfunktionen von Skype for Business Online benötigen Sie (neben Ihrem eigenen) mindestens zwei weitere Konten. 
    
## <a name="set-up-test-computers"></a>Einrichten von Testcomputern
<a name="__toc328126911"> </a>

Auf jedem Testcomputer:
  
1. Wechseln Sie zur Homepage von Office 365, und melden Sie sich mit den Anmeldeinformationen eines Ihrer Testkonten an.
    
2. Wechseln Sie zu **Einstellungen**![Einstellungen: Profil aktualisieren, Software installieren und mit der Cloud verbinden](../images/4b83e9cb-c7e4-46c8-b3d1-cfee017123ae.png), und klicken Sie dann auf **Software installieren und mit der Cloud verbinden**. 
    
## <a name="set-up-audio-conferencing"></a>Einrichten von Audiokonferenzen
<a name="__toc328126912"> </a>

Richten Sie ein Konto bei einem Audiokonferenzanbieter ein, um den Zugriff per Telefon auf Skype for Business Online-Besprechungen zu ermöglichen. Damit erhalten Sie Folgendes:
  
- Gebührenpflichtige Einwahlnummern und gegebenenfalls gebührenfreie Telefonnummern.
    
- Für jeden Benutzer in der Organisation, der Besprechungen plant oder moderiert, einen Konferenzcode und eine PIN (persönliche Identifikationsnummer).
    
Nachdem Sie die Benutzer für Audiokonferenzen eingerichtet haben, erhalten sie eine automatisierte E-Mail-Nachricht mit den Einwahlnummern und dem Konferenzcode. Diese Informationen werden auch automatisch allen neuen Skype for Business-Besprechungsanfragen hinzugefügt.
  
Details finden Sie unter [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing.md). 
  
 **So fügen Sie dem Konto eines Ihrer Testbenutzer Audiokonferenzinformationen hinzu**
  
1. Click **Audio Conferencing** > **Uusers**.
    
2. Klicken Sie auf die Namen der Benutzer, für die Sie Einwahlkonferenzen einrichten möchten, und klicken Sie dann auf **Bearbeiten**![Bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).
    
3. Wählen Sie den Audiokonferenzanbieter aus, geben Sie die erforderlichen Informationen ein und klicken Sie auf **Speichern**.
    
|**Audiokonferenzeinstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbieter** <br/> |Wählen Sie Ihren Audiokonferenzanbieter aus der Liste aus.  <br/> |
|**Gebührenpflichtige Nummer** (erforderlich) <br/> |Die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Formatieren Sie die Nummern so, wie sie in den Skype for Business-Besprechungseinladungen angezeigt werden sollen.  <br/> |
|**Gebührenfreien Nummer** <br/> |Die Telefonnummern, die Sie vom Audiokonferenzanbieter erhalten haben. Formatieren Sie die Nummern so, wie sie in den Skype for Business-Besprechungseinladungen angezeigt werden sollen.  <br/> |
|**Kenncode** <br/> |Der Kenncode (Konferenzcode) für diesen Benutzer.  <br/> |
   
## <a name="test-skype-for-business-online-features-and-devices"></a>Testen der Funktionen und Geräte von Skype for Business Online
<a name="__toc328126913"> </a>

Vergewissern Sie sich, dass die wichtigsten Funktionen von Skype for Business Online wie erwartet funktionieren.
  
 **Anmelden und Abmelden**
  
|**Aufgabe**|**Erwartetes Ergebnis**|
|:-----|:-----|
|[An- und Abmelden bei Lync Online](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Das Skype for Business-Hauptfenster wird mit dem Anwesenheitsstatus angezeigt, den Sie bei der Anmeldung angegeben haben.  <br/> |
|[An- und Abmelden bei Lync Online](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Der Skype for Business-Anmeldebildschirm wird angezeigt.  <br/> |
|[An- und Abmelden bei Lync Online](http://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Das Skype for Business-Fenster wird geschlossen und das Skype for Business-Symbol wird nicht mehr im Windows-Benachrichtigungsbereich angezeigt.  <br/> |
   
Sie können sich nicht anmelden? Weitere Informationen finden Sie unter [Behebung von Anmeldungsproblemen in Skype for Business Online](https://support.microsoft.com/kb/2541980).
  
 **Kontakte, Anwesenheitsstatus und Chatunterhaltungen**
  
|**Aufgabe**|**Erwartetes Ergebnis**|
|:-----|:-----|
|[Senden einer Chatnachricht in Skype for Business](http://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Das Skype for Business-Unterhaltungsfenster wird angezeigt, Sie geben etwas ein und empfangen eine Antwort von der Person, mit der Sie sich in Verbindung gesetzt haben.  <br/> |
|[Senden einer Chatnachricht in Skype for Business](http://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Das Skype for Business-Unterhaltungsfenster wird angezeigt, Sie machen eine Eingabe und erhalten Antworten von allen Teilnehmern der Unterhaltung.  <br/> |
|[Suchen nach einem Kontakt anhand des Vor- oder Nachnamens](https://support.office.live.com/article/29fa2061-f679-4e0d-902d-736b67774c8b#BKMK_ContactsFAQ) <br/> |Die Anzeige der Suchergebnisse beginnt, sobald Sie mit der Eingabe beginnen.  <br/> |
|[Häufig gestellte Fragen zu Lync für Office 365](http://support.office.com/article/29fa2061-f679-4e0d-902d-736b67774c8b.aspx#BKMK_ContactsFAQ) <br/> |Der hinzugefügte Kontakt wird in der von Ihnen ausgewählten Gruppe „Kontakte" angezeigt.  <br/> |
|[Ändern Ihres Anwesenheitsstatus in Skype for Business (Lync)](http://support.office.com/article/ef8998cc-7801-4b62-81ba-9a2c1630f9e5) <br/> |Ihr neuer Anwesenheitsstatus wird in den Kontaktlisten der anderen Teilnehmer angezeigt.  <br/> |
|[Verwenden der Visitenkarte](http://support.office.com/article/19870880-FC90-46B0-9C60-C398518E9FBC) <br/> |Die Visitenkarte einer Person wird neben ihrem Namen angezeigt.  <br/> |
   
 **Anrufe zwischen zwei Personen**
  
|**Aufgabe**|**Erwartetes Ergebnis**|
|:-----|:-----|
|[Ausführen und Entgegennehmen eines Lync-Audioanrufs](http://support.office.com/article/39342f16-4d16-44de-a806-0b2b566f3886) <br/> |Das Unterhaltungsfenster wird angezeigt, und Sie hören das Rufzeichen. Die angerufene Person wird auf ihrem Desktop benachrichtigt und nimmt den Anruf an. Das Unterhaltungsfenster wird aktualisiert, sobald die Verbindung hergestellt wurde.  <br/> |
|[Hinzufügen von Audio zu einer Chatunterhaltung in Skype for Business (Lync)](http://support.office.com/article/21a098b2-63f1-4205-a9aa-532b6a67ea92) <br/> |Die Verbindung wird hergestellt und Sie können mit der anderen Person chatten und sprechen.  <br/> |
|[Freigeben Ihres Desktops oder eines Programms in Lync](http://support.office.com/article/33aaa965-eb32-42a9-8a9b-cdfffa364842) <br/> |Der freigegebene Desktop oder das freigegebene Programm der anderen Person wird angezeigt.  <br/> |
   
 **Konferenzen**
  
|**Aufgabe**|**Erwartetes Ergebnis**|
|:-----|:-----|
|[Einrichten einer Lync-Besprechung](http://support.office.com/article/258f9d20-f06c-49a4-a77f-7f5ac635bb5d) <br/> |Eine Besprechungseinladung wird an die von Ihnen angegebenen Personen gesendet.  <br/> |
|[Ändern von Teilnehmereinstellungen für Skype for Business (Lync)-Besprechungen](http://support.office.com/article/cee2aa78-d878-4a63-ad33-9c249fceced9) <br/> |Abhängig von der Option.  <br/> **TIPP:** Unter **Zugriff und Referenten** können Sie mit verschiedenen Einstellungen der Option **Wer kann den Wartebereich umgehen** experimentieren. <br/> |
|[Teilnehmen an einer Skype for Business (Lync)-Besprechung](http://support.office.com/article/538716dc-f4f2-48c2-af96-587c62387b87) <br/> |Das Unterhaltungsfenster wird geöffnet und Ihr Name wird nach dem Herstellen der Verbindung in der Liste der Besprechungsteilnehmer angezeigt.  <br/> |
|[Stummschalten oder Aufheben der Stummschaltung Ihres Mikrofons in einer Skype for Business-Besprechung oder bei einem Anruf](http://support.office.com/article/47399948-db7f-4ee5-8e61-53a94bb97704) <br/> |Das Symbol „Stumm geschaltet" wird neben den Namen aller Teilnehmer in der Besprechungsteilnehmerliste angezeigt. Nur Sie werden gehört, wenn Sie sprechen.  <br/> |
|[Präsentieren von PowerPoint-Folien in einer Skype for Business (Lync)-Besprechung](http://support.office.com/article/3910a2b2-01df-4b97-9451-322b598ede7e) <br/> |Ihre PowerPoint-Präsentation wird auf den Computern aller Teilnehmer im Skype for Business-Besprechungsfreigabefenster angezeigt.  <br/> |
|[Übertragen einer Datei in einer Skype for Business (Lync)-Besprechung](http://support.office.com/article/f6942910-bc1d-4a48-bf18-385778f08088) <br/> |Nach dem Hochladen können alle Teilnehmer in der Besprechung die Anlage anzeigen und herunterladen.  <br/> |
   
## <a name="related-topics"></a>See Also
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
