---
title: Verwalten der App "Lob" im Teams Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jozhuan
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informationen zu Administratoreinstellungen in der App "Lob" im Microsoft Teams Admin Center
ms.openlocfilehash: becaccc9c8370d25e3d085e3c896d4f1a8a0ad95
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995183"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der App "Lob" im Microsoft Teams Admin Center

> [!NOTE]
> Administratoren müssen über eine Teams-Lizenz verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne Eine Teams-Lizenz auf dieses Feature zu zugreifen, wird eine Fehlermeldung angezeigt.

Die App "Lob" in Microsoft Teams hilft Benutzern, Mitgliedern ihrer Organisation oder ihres Klassenzimmers Anerkennung zu zeigen. Mit einer Auswahl von Signalsätzen zur Auswahl und der Möglichkeit, eigene Badges zu erstellen, soll Lob dazu beitragen, den Aufwand zu erkennen, der in die breite Palette der Arbeit geht, die Teams-Benutzer von Lehrkräften bis zu Frontline-Mitarbeitern unternehmen. Weitere Informationen finden Sie unter [Senden von Lob an Personen.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Administratoren können über das Microsoft Teams Admin Center steuern, welche Badges für ihre Organisation verfügbar sind. Wechseln Sie in der linken Navigationsleiste zu **Teams-Apps > Verwalten von Apps.** Klicken Sie in der Liste der Apps auf **Lob**, und wählen Sie dann **Einstellungen aus.**  Hier können Sie standard- und integrierte Signalsätze aktivieren und benutzerdefinierte Badges erstellen.

![Screenshot der Registerkarte Einstellungen für die App "Lob"](media/manage-praise-app-settings.png)

> [!NOTE]
> Das Feature "App loben" steht für Us-Government-Clouds nicht zur Verfügung.

## <a name="use-built-in-badge-sets"></a>Verwenden integrierter Signalsätze

Integrierte Sätze sind Sammlungen von Signalen, die von Microsoft für die App "Lob" entworfen wurden. Diese Sätze können von Administratoren nicht bearbeitet werden. Der Standardabzeichensatz ist bereits aktiviert und in der App Lob verfügbar. Um die Verfügbarkeit des Standardsets oder aller Signalsätze zu ändern, schalten Sie die entsprechende Umschaltweise auf Ein oder Aus um. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Standardabzeichen

Der Standardabzeichensatz soll Teams-Benutzern dabei helfen, ihre Peers zu erkennen, damit sie mit ihrer Arbeit über die Grenzen hinaus gehen.

![Vorschau auf den Standardabzeichensatz](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Soziale und emotionale Lernabzeichen für Bildungseinrichtungen

Pädagogen können einzelne Schüler/Studenten für Leistungen und Verhaltensweisen für soziales und emotionales Lernen (SOCIAL And Emotional Learning, SEL) mit Signalen erkennen, die diese Konzepte veranschaulichen.

![Vorschau auf die Sozialen und emotionalen Lernabzeichen für Bildungseinrichtungen](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Erstellen eigener Badges

Wählen **Sie Benutzerdefiniertes Signal erstellen aus.** Hier können Sie ein benutzerdefiniertes Signal im Seitenbereich entwerfen. Sie können bis zu 25 benutzerdefinierte Badges erstellen. 

![Screenshot des Bereichs "Benutzerdefiniertes Signal erstellen"](media/manage-praise-app-create-custom-badge.png)

1. Geben Sie einen Signalnamen ein. Dies ist der Name, der auf dem Signal angezeigt wird, wenn Benutzer Lob senden.

2. Legen Sie die Signalfarben ein. Zum Festlegen der Text- und Hintergrundfarben des Signals müssen Sie die Farben als hexadezimale Werte (Hex) eingeben.

   > [!TIP]
   > Wenn Sie mit Hexwerten noch nicht [](#hex-colors-intro) so weit sind, enthält dieser Artikel eine kurze Einführung, die Ihnen zeigt, wie Sie sie verwenden.

3. Laden Sie ein Signalbild hoch. Der akzeptierte Dateityp ist . PNG. Die Bilddatei muss kleiner als 40 KB sein und maximal 216 x 216 Pixel groß sein.
![Signal mit Beschriftung von Hintergrund-, Text- und Bildfeldern](media/praise-app-badge-fields.png)

4. Lokalisieren Des Signalnamens: Wählen Sie unter **Lokalisierte Signalnamen** die Option **Hinzufügen aus.** Wählen Sie in der Dropdownliste das gewünschte Locale aus. Geben Sie dann den Signalnamen in der vorgesehenen Sprache ein.

5. Schließen Sie Ihr Signal von bestimmten Locales aus: Wählen Sie unter Signal von diesen **Locales** ausschließen die Option **Hinzufügen aus.** Wählen Sie die Locales aus, die Sie aus der Dropdownliste ausschließen möchten.

6. Wählen Sie **Übernehmen aus.** Ihr neues Signal wird nun in der Tabelle "Benutzerdefinierte Badges" angezeigt.

> [!NOTE]
> Wenn die Schritte 4 und 5 übersprungen werden, wird das Signal in der Standardsprache für alle Locales angezeigt.
>
> Wenn Sie mit dem Vornehmen von Änderungen an ihrer Signalauswahl fertig sind, stellen Sie sicher, dass Sie **Absenden auswählen.** Es kann bis zu ein paar Stunden dauern, bis diese Änderungen für Ihre Organisation verfügbar sind.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Angeben von Farben mit Hexwerten

Hexfarbenwerte sind Zeichenfolgen mit sechs hexadezimalen Ziffern, die die Intensität von Rot (RR), Grün (GG) und Blau (BB) in einer bestimmten Farbe auf einer Skala von 00 bis FF darstellen. Wenn Sie die Werte aller drei Farben zusammenbringen, erhalten Sie einen Hexwert: #RRGGBB

Beispielsweise ist der Hexwert für die Farbe Rot #FF0000 da Rot auf den höchstmöglichen Wert festgelegt ist, FF und Grün und Blau jeweils auf den niedrigsten möglichen Wert 00 festgelegt werden.

Wenn Sie verschiedene Farben und deren Hexadezimalwerte erkunden können, schauen Sie sich [die Bing-Farbauswahl an.](https://www.bing.com/search?q=color+picker)

Im Folgenden finden Sie eine Liste der Beispielfarben für die ersten Schritte:

|Farbe  |Hexwert|
|-------|---------|
|![Hexfarben #FF6666](media/hexColor1.png)|  #FF6666   |
|![Hexfarben #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![Hexfarben #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![Hexfarben #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![Hexfarben #800080](media/hexColor5.png)|  #800080   |
|![Hexfarben #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Bewährte Methoden zum Erstellen von benutzerdefinierten Signalen

**Senden Sie alle Ihre Badges auf einmal.** Da es eine Weile dauert, bis neue Badges verarbeitet werden, ist es am besten, alle Ihre benutzerdefinierten Badges zur Tabelle hinzuzufügen, bevor Sie sie übermitteln.

**Beachten Sie bei der Auswahl von Farben die Barrierefreiheit.** Einige Farben sind besser zusammen als andere.  Erstellen Sie Kontrast zwischen Text und Hintergrundfarben, damit der Signalname leicht zu lesen ist. Wenn Sie beispielsweise eine dunkle Hintergrundfarbe ausgewählt haben, wählen Sie eine helle Textfarbe aus.

**Beachten Sie beim Auswählen eines Bilds die Abmessungen des Signals.** Um die beste Qualität zu gewährleisten, empfehlen wir, eine Bilddatei hochzuladen, die 216 x 216 Pixel (die maximalen Abmessungen) hat. Vermeiden Sie das Dehnen oder Verzerren des Bilds, um diese Abmessungen zu passen.

**Wenn Ihr Signalbild nicht rechteckig ist, machen Sie das Bild transparent.** Sie müssen dies tun, bevor Sie die Bilddatei in Lob hochladen.

![Links: Signal mit nicht transparentem Bild, rechts: Signal mit transparentem Bild](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ressourcen für Signalsatz

Integrierte Signalsätze können nicht geändert werden. Wenn also ein integrierter Satz aktiviert ist, werden alle Badges im Satz der App Lob hinzugefügt. Wenn Sie bestimmte Badges aus einem integrierten Satz hinzufügen und andere aus lassen möchten, erstellen Sie die Badges, die Sie als benutzerdefinierte Badges verwenden möchten, erneut. Sie können das Signalbild herunterladen und den Text und die Hintergrundfarben von Signalen aus integrierten Sätzen in den folgenden Tabellen finden.

### <a name="default-badges-assets"></a>Standard-Badges-Ressourcen

</br>

|Signalname     |Bilddatei  |Textfarbe | Hintergrundfarbe |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Prima        |[Tolle PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Coach          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Mut        |[Png 'Mut'](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Kreativ       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inklusiv      |[Inklusive PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimismus       |[Png "Optimismus"](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Problemlöser |[Problemlöser PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Teamplayer    |[TEAMPLAYER PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Danke      |[Vielen Dank PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Soziale und emotionale Lernabzeichen für Bildungsressourcen

</br>

|Signalname        |Bilddatei  |Textfarbe | Hintergrundfarbe |
|------------------|------------|---------- |--------|
|Kommunikation     |[Kommunikation PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Kritisches Denken |[PNG für kritisches Denken](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Neugier         |[Curiosity PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathie           |[Empathie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Zielstrebung      |[ZIELVERFOLGUNG PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivation        |[Motivation PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenz       |[Persistenz PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Respekt           |[Achten Sie auf PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Verantwortung    |[Verantwortung PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Selbsterklingung    |[PNG zur Selbstwahrrheit](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Selbstverwaltung   |[PNG zur Selbstverwaltung](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Nachdenklichkeit    |[Nachdenklichkeit PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
