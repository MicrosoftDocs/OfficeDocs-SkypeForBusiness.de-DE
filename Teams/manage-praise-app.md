---
title: Verwalten der Lob-App im Teams Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jozhuan
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informationen zu den Administratoreinstellungen in der Lob-App im Microsoft Teams Admin Center
ms.openlocfilehash: 52dbadcc20e1c73d48d5f5b7f762493f2dd61c64aa29e7a924e03dd09c63bed6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278134"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der Lob-App im Microsoft Teams Admin Center

> [!NOTE]
> Administratoren müssen über eine Lizenz Teams verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie ohne Lizenz auf dieses Feature Teams, wird eine Fehlermeldung angezeigt.

Die Lob-App in Microsoft Teams dabei, den Mitgliedern ihrer Organisation oder ihres Klassenzimmers Anerkennung zu zeigen. Mit einer Auswahl von Badge-Sätzen und der Option zum Erstellen eigener Badges soll Lob helfen, den Aufwand zu erkennen, der für die breite Palette an Arbeit, die Teams-Benutzern gilt, von Lehrkräften bis zu Frontline Workers fällt. Weitere Informationen finden Sie unter [Senden Lob an Personen.](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Administratoren können über das Admin Center steuern, welche Badges für Microsoft Teams verfügbar sind. Navigieren Sie im linken Navigationsbereich zu Teams **Apps > Apps verwalten**. Klicken Sie in der Liste der Apps **auf Lob**, und wählen Sie dann **Einstellungen** aus.  Von hier aus können Sie standard- und integrierte Signalsätze aktivieren und benutzerdefinierte Badges erstellen.

![Screenshot der Einstellungen für die App Lob App](media/manage-praise-app-settings.png)

> [!NOTE]
> Das Lob"-App ist für US-Regierung clouds nicht verfügbar.

## <a name="use-built-in-badge-sets"></a>Verwenden von integrierten Signalsätzen

Integrierte Gruppen sind Sammlungen von Signalen, die von Microsoft für die App Lob wurden. Diese Gruppen können von Administratoren nicht bearbeitet werden. Der Standardabzeichensatz ist bereits aktiviert und in der App Lob verfügbar. Um die Verfügbarkeit des Standard-Sätzes oder von Signalsätzen zu ändern, setzen Sie den entsprechenden Umschalter auf Ein oder Aus. 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Standardabzeichen

Der Standardabzeichensatz soll es Teams Benutzern zu ermöglichen, ihre Kollegen zu erkennen, damit sie mit ihrer Arbeit über- und hinaus gehen können.

![Vorschau auf den Standardabzeichensatz](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Soziale und emotionale Lernabzeichen für Bildungseinrichtungen

Lehrkräfte können einzelne Schüler/Studenten für sociale und emotionale Lernerfolge (SEL) mit Signalen erkennen, die diese Konzepte veranschaulichen.

![Vorschau der Sozialen und emotionalen Lernabzeichen für Bildungseinrichtungen](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Erstellen eigener Badges

Wählen **Sie Benutzerdefiniertes Signal erstellen aus.** Hier können Sie im Seitenbereich ein benutzerdefiniertes Signal entwerfen. Sie können bis zu 25 benutzerdefinierte Badges erstellen. 

![Screenshot des Bereichs "Benutzerdefiniertes Signal erstellen"](media/manage-praise-app-create-custom-badge.png)

1. Geben Sie einen Badgenamen ein. Dies ist der Name, der im Signal angezeigt wird, wenn Benutzer Lob senden.

2. Legen Sie die Signalfarben festgelegt. Zum Festlegen der Text- und Hintergrundfarben ihres Badges müssen Sie die Farben als hexadezimale (hexadezimale) Werte eingeben.

   > [!TIP]
   > Wenn Sie mit Hexadezimalwerten noch [](#hex-colors-intro) nicht aus dem Weg sind, finden Sie in diesem Artikel eine kurze Einführung in deren Verwendung.

3. Hochladen eines Signalbilds. Der akzeptierte Dateityp ist .PNG. Die Bilddatei muss weniger als 40 KB groß sein und maximal 216 x 216 Pixel groß sein.
![Signal mit Beschriftungsfeldern für Hintergrund, Text und Bild](media/praise-app-badge-fields.png)

4. Lokalisieren Sie den Signalnamen: Wählen Sie unter **Lokalisierte Signalnamen** die Option **Hinzufügen aus.** Wählen Sie das gewünschte Locale aus der Dropdownliste aus. Geben Sie dann den Badgenamen in der festgelegten Sprache ein.

5. Schließen Sie Ihr Signal aus bestimmten Länder/Sprachen aus: Wählen Sie unter Signal von diesen **Länder ausschließen** die Option **Hinzufügen aus.** Wählen Sie die Lokalen aus, die Sie aus der Dropdownliste ausschließen möchten.

6. Wählen Sie **Übernehmen aus.** Das neue Signal wird jetzt in der Tabelle mit den benutzerdefinierten Signalen angezeigt.

> [!NOTE]
> Wenn die Schritte 4 und 5 übersprungen werden, wird das Signal in der Standardsprache für alle Locales angezeigt.
>
> Wenn Sie alle Änderungen an Ihrer Signalauswahl vorgenommen haben, müssen Sie Absenden **auswählen.** Es kann einige Stunden dauern, bis diese Änderungen für Ihre Organisation zur Verfügung stehen.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Angeben von Farben mit Hexadezimalwerten

Hexadezimalfarbwerte sind Zeichenfolgen mit sechs Hexadezimalziffern, die die Intensität von Rot (RR), Grün (GG) und Blau (BB) in einer bestimmten Farbe auf einer Skala von 00 bis FF darstellen. Wenn Sie die Werte aller drei Farben zusammenbringen, erhalten Sie einen Hexadezimalwert: #RRGGBB

Beispielsweise ist der Hexadezimalwert für die Farbe Rot #FF0000, da Rot auf den höchsten möglichen Wert festgelegt wird, FF und Grün und Blau jeweils auf den niedrigsten möglichen Wert, 00.

Informationen zu unterschiedlichen Farben und deren Hexadezimalwerten Bing [die Farbauswahl.](https://www.bing.com/search?q=color+picker)

Im Folgenden finden Sie eine Liste mit Beispielfarben für die ersten Schritte:

|Farbe  |Hexadezimalwert|
|-------|---------|
|![Hex color #FF6666](media/hexColor1.png)|  #FF6666   |
|![Hex color #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![Hex color #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![Hex color #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![Hex color #800080](media/hexColor5.png)|  #800080   |
|![Hex color #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Bewährte Methoden zum Erstellen benutzerdefinierter Badges

**Senden Sie alle Badges auf einmal.** Da die Verarbeitung neuer Badges eine Weile dauert, sollten Sie am besten alle benutzerdefinierten Badges zur Tabelle hinzufügen, bevor Sie sie übermitteln.

**Beachten Sie bei der Auswahl von Farben die Barrierefreiheit.** Einige Farben sind besser zusammen als andere.  Stellen Sie einen Kontrast zwischen Text- und Hintergrundfarben sicher, damit der Signalname leichter zu lesen ist. Wenn Sie beispielsweise eine dunkle Hintergrundfarbe ausgewählt haben, wählen Sie eine helle Textfarbe aus.

**Behalten Sie beim Auswählen eines Bilds die Signalabmessungen im Auge.** Für eine optimale Qualität empfehlen wir, eine Bilddatei mit einer Größe von 216 x 216 Pixel (die maximalen Abmessungen) hochzuladen. Vermeiden Sie es, das Bild zu dehnen oder zu verzerren, damit es in diese Abmessungen passt.

**Wenn das Signalbild nicht rechteckig ist, machen Sie das Bild transparent.** Sie müssen dies tun, bevor Sie die Bilddatei in das Lob.

![Links: Signal mit nicht transparentem Bild, rechts: Signal mit transparentem Bild](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ressourcen für Signalsatz

Integrierte Signalsätze können nicht geändert werden. Wenn ein integrierter Satz aktiviert ist, werden alle Badges im Satz der App Lob hinzugefügt. Wenn Sie bestimmte Badges aus einem integrierten Satz hinzufügen und andere aus lassen möchten, erstellen Sie die Badges, die Sie als benutzerdefinierte Badges verwenden möchten, erneut. Sie können das Signalbild herunterladen und den Text und die Hintergrundfarben von Signalen aus den integrierten Gruppen in den folgenden Tabellen suchen.

### <a name="default-badges-assets"></a>Standardressourcen für Badges

</br>

|Signalname     |Bilddatei  |Textfarbe | Hintergrundfarbe |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Prima        |[Fantastische PNG-Datei](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Coach          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Yrn        |[Png-Datei für "Png"](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Kreativ       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inklusive      |[Inklusive PNG-Datei](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Durchdingen       |[Png-Datei](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Problemlösung |[PNG für Problemlösungs-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Teamplayer    |[Teamplayer PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Danke      |[Vielen Dank!PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Soziale und emotionale Lernabzeichen für Bildungsressourcen

</br>

|Signalname        |Bilddatei  |Textfarbe | Hintergrundfarbe |
|------------------|------------|---------- |--------|
|Kommunikation     |[Kommunikations-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Kritisches Denken |[Critical thinking PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Kuriose         |[Png mit Interesse für die Neugierige](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Einfühlungsvermögen           |[Empathie PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Zielstrebung      |[Ziel-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivation        |[Motivations-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenz       |[Persistenz-PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Respekt           |[PNG-Datei respektieren](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Verantwortlichkeit    |[Verantwortung PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Selbsterklingung    |[PNG-Datei mit Selbsterwahrde](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Selbstverwaltung   |[PNG-Datei zur Selbstverwaltung](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thought vermeinen    |[Thought vermeinen PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
