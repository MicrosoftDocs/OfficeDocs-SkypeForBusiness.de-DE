---
title: Verwalten der Lob-App im Team Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informationen zu den Administratoreinstellungen in der Lob-App im Microsoft Teams Admin Center
ms.openlocfilehash: 27206f48de9c219996f8dcfd631e6640e175fb18
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580451"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der Lob-App im Microsoft Teams Admin Center

> [!NOTE]
> Administratoren müssen über eine Teams-Lizenz verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne eine Teams-Lizenz auf dieses Feature zuzugreifen, erhalten Sie eine Fehlermeldung.

Die Lob-app in Microsoft Teams hilft Benutzern, die Mitglieder Ihrer Organisation oder Ihres Klassenzimmers zu schätzen. Mit einer Auswahl von Signal Sätzen, die Sie auswählen können, und der Möglichkeit, ihre eigenen Badges zu erstellen, soll das Lob dazu beitragen, die Anstrengung zu erkennen, die in die breite Palette der Arbeit, die die Benutzer von Teams tun, eingeht, von Pädagogen bis zu Mitarbeitern in erster Linie.

Administratoren können über das Team Admin Center steuern, welche Abzeichen für Ihre Organisation zur Verfügung stehen. Wählen Sie im linken Navigationsbereich die Option **Teams-apps > apps verwalten**aus. Öffnen Sie Lob im [Mandanten-App-Katalog](https://docs.microsoft.com/microsoftteams/manage-apps#view-apps-in-your-tenant-app-catalog), und wechseln Sie zu **Einstellungen**.

> [!NOTE]
> Das Lob-App-Feature steht für Clouds der US-Regierung nicht zur Verfügung.

## <a name="use-built-in-badge-sets"></a>Verwenden integrierter Signal Sätze

Integrierte Sätze sind Sammlungen von Abzeichen, die von Microsoft für die Lob-app entwickelt wurden. Diese Sätze können von Administratoren nicht bearbeitet werden. Der standardmäßige Badge-Satz ist bereits aktiviert und in der Lob-app verfügbar. Wenn Sie die Verfügbarkeit des Standardsatzes oder von Signal Sätzen ändern möchten, schalten Sie den entsprechenden Schalter auf ein oder aus. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Standard-Badges

Der standardmäßige Badge-Satz dient dazu, Teams Benutzern zu helfen, ihre Kollegen zu erkennen, dass Sie mit ihrer Arbeit darüber hinausgehen.

![Vorschau des standardmäßigen Badge-Satzes](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Social-und emotional Learning-Abzeichen für Bildungseinrichtungen

Pädagogen können einzelne Schüler für soziale und emotionale Lernziele (SEL) und Verhaltensweisen mit Abzeichen erkennen, die diese Konzepte veranschaulichen.

![Vorschau auf die Social-und emotional Learning-Abzeichen für Bildungseinrichtungen](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Erstellen eigener Badges

Wechseln Sie zum Schalter **benutzerdefinierte Badges** zu ein, und wählen Sie **benutzerdefiniertes Badge erstellen**aus. Von dort aus können Sie ein benutzerdefiniertes Badge im Seitenbereich entwerfen. Sie können bis zu 25 benutzerdefinierte Badges erstellen. 

1. Geben Sie einen Badge-Namen ein. Dies ist der Name, der auf dem Badge angezeigt wird, wenn Nutzer Lob senden.

2. Setzen Sie Ihre Abzeichen-Farben. Wenn Sie die Text-und Hintergrundfarben Ihres Badges einstellen möchten, müssen Sie die Farben als Hexadezimalwerte (Hex) eingeben.

   > [!TIP]
   > Wenn Sie mit Hex-Werten noch nicht vertraut sind, finden Sie in diesem Artikel eine [kurze Einführung](#hex-colors-intro) , die Ihnen zeigt, wie Sie Sie verwenden.

3. Hochladen eines Badge-Bilds Der akzeptierte Dateityp ist. PNG. Die Bilddatei muss kleiner als 40 KB mit Maximalabmessungen von 216 X 216 Pixeln sein.
![Abzeichen mit beschrifteten Feldern für Hintergrund, Text und Bild](media/praise-app-badge-fields.png)

4. Lokalisieren Sie Ihren Badge-Namen: Wählen Sie unter **lokalisierte Signalnamen**die Option **Hinzufügen**aus. Wählen Sie in der Dropdownliste das gewünschte Gebietsschema aus. Geben Sie dann den Namen des Signals in der angegebenen Sprache ein.

5. Schließen Sie Ihre Plakette von bestimmten Gebietsschemas ab: Wählen Sie unter **Badge aus diesen Gebietsschemas ausschließen**die Option **Hinzufügen**aus. Wählen Sie in der Dropdownliste die Gebietsschemas aus, die Sie ausschließen möchten.

6. Wählen Sie über **nehmen**aus. Ihr neues Badge wird nun in der Tabelle benutzerdefinierte Badges angezeigt.

> [!NOTE]
> Wenn die Schritte 4 und 5 übersprungen werden, befindet sich das Badge in der Standardsprache für alle Gebietsschemas.
>
> Wenn Sie mit dem vornehmen von Änderungen an der Badge-Auswahl fertig sind, stellen Sie sicher, dass Sie **Submit**auswählen. Es kann bis zu einigen Stunden dauern, bis diese Änderungen für Ihre Organisation verfügbar sind.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Angeben von Farben mit Hex-Werten

Hexadezimale Farbwerte sind Zeichenfolgen mit sechs hexadezimalen Ziffern, die die Intensität von rot (RR), grün (GG) und blau (BB) in einer bestimmten Farbe auf einer Skala von 00 bis FF darstellen. Wenn Sie die Werte aller drei Farben zusammensetzen, erhalten Sie einen Hex-Wert: #RRGGBB

Beispielsweise ist der Hex-Wert für die Farbe Rot #FF0000, da rot mit dem höchstmöglichen Wert, FF, und grün und blau auf den niedrigsten möglichen Wert 00 gesetzt sind.

Wenn Sie unterschiedliche Farben und ihre Hex-Werte erkunden möchten, lesen Sie [Bing-Farbauswahl](https://www.bing.com/search?q=color+picker).

Nachfolgend finden Sie eine Liste mit Beispielfarben, die Ihnen den Einstieg verschaffen:

|Farbe  |Hex-Wert|
|-------|---------|
|![Hex-Farbe #FF6666](media/hexColor1.png)|  #FF6666   |
|![Hex-Farbe #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![Hex-Farbe #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![Hex-Farbe #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![Hex-Farbe #800080](media/hexColor5.png)|  #800080   |
|![Hex-Farbe #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Bewährte Methoden zum Erstellen von benutzerdefinierten Signalen

**Senden Sie alle ihre Abzeichen auf einmal.** Da es eine Weile dauert, bis neue Abzeichen verarbeitet werden, empfiehlt es sich, alle Ihre benutzerdefinierten Badges zur Tabelle hinzuzufügen, bevor Sie Sie übermitteln.

**Bei der Auswahl von Farben sollten Sie die Barrierefreiheit berücksichtigen.** Einige Farben gehen besser zusammen als andere.  Erstellen Sie einen Kontrast zwischen Ihren Text-und Hintergrundfarben, damit der Badge-Name einfach lesbar ist. Wenn Sie beispielsweise eine dunkle Hintergrundfarbe ausgewählt haben, wählen Sie eine hell Text Farbe aus.

**Beachten Sie bei der Auswahl eines Bilds die Abzeichen-Bemaßungen.** Für eine optimale Qualität empfehlen wir, eine Bilddatei hochzuladen, bei der es sich um 216 x 216 Pixel (maximale Abmessungen) handelt. Vermeiden Sie es, das Bild zu dehnen oder zu verzerren, damit es in diese Maße passt.

**Wenn Ihr Badge-Bild nicht rechteckig ist, machen Sie das Bild transparent.** Sie müssen dies tun, bevor Sie die Bilddatei zum Lob hochladen.

![Links: Abzeichen mit nicht transparentem Bild, rechts: Abzeichen mit transparentem Bild](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Signal Satz Ressourcen

Integrierte Signal Sätze können nicht geändert werden, wenn ein integrierter Satz aktiviert ist, werden alle Badges in der Gruppe der Lob-app hinzugefügt. Wenn Sie bestimmte Abzeichen aus einem integrierten Satz hinzufügen und andere Personen auslassen möchten, erstellen Sie die Badges, die Sie als benutzerdefinierte Abzeichen verwenden möchten, erneut. Sie können das Badge-Bild herunterladen und die Text-und Hintergrundfarben von Abzeichen aus integrierten Sätzen in den folgenden Tabellen finden.

### <a name="default-badges-assets"></a>Standardmäßige Badges-Ressourcen

</br>

|Badge-Name     |Image-Datei  |Textfarbe | Hintergrundfarbe |
|---------------|------------|---------- |--------|
|Achiever       |[Überflieger-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Prima        |[Awesome PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Trainer          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Mut        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Kreativ       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inclusive      |[Inklusive PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Gutherziges Herz     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Führerschaft     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimismus       |[Optimismus PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Problem Löser |[Problem Löser PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Team Player    |[Team Player PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Danke      |[Vielen Dank PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Social-und emotional Learning-Abzeichen für Bildungsressourcen

</br>

|Badge-Name        |Image-Datei  |Textfarbe | Hintergrundfarbe |
|------------------|------------|---------- |--------|
|Kommunikation     |[Kommunikation PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Kritisches Denken |[Kritisches Denken PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Neugier         |[Kuriosität PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Empathie           |[Empathie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Zielverfolgung      |[Ziel Verfolgungs-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivation        |[Motivations-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenz       |[Persistenz PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Bezug           |[Achten Sie auf PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Verantwortung    |[Verantwortlichkeit PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Selbsterkenntnis    |[Self-Awareness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Selbstverwaltung   |[Self-Management PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Nachdenklichkeit    |[Nachdenklichkeit PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
