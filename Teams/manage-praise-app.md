---
title: Verwalten der App "Lob" im Teams Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: Informationen zu den Administratoreinstellungen in der App "Lob" im Microsoft Teams Admin Center
ms.openlocfilehash: 122e7f0ffad914e62ede56ebd1811d1504f3fcd7
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909189"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Verwalten der App "Lob" im Microsoft Teams Admin Center

> [!NOTE]
> Administratoren müssen über eine Lizenz für Teams verfügen, um auf dieses Feature zugreifen zu können. Wenn Sie versuchen, ohne eine Teams-Lizenz auf dieses Feature zu zugreifen, wird eine Fehlermeldung angezeigt.

Die App "Lob" in Microsoft Teams hilft Benutzern, Mitgliedern ihrer Organisation oder ihres Klassenzimmers Anerkennung zu zeigen. Mit einer Auswahl von Signalsätzen zur Auswahl und der Option zum Erstellen eigener Badges soll Lob dazu beitragen, die Mühe zu erkennen, die in die breite Palette an Arbeit, die Benutzer von Teams abarbeiten, von Lehrkräften bis zu Frontlinemitarbeitern fällt. Weitere Informationen finden Sie unter "Lob [an Personen senden".](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)

Administratoren können über das Microsoft Teams Admin Center steuern, welche Badges für ihre Organisation verfügbar sind. Navigieren Sie in der linken Navigationsleiste zu **"Teams-Apps" > "Apps verwalten".** Klicken Sie in der Liste der Apps auf **"Lob",** und wählen Sie **"Einstellungen" aus.**  Von hier aus können Sie standard- und integrierte Signalsätze aktivieren und benutzerdefinierte Badges erstellen.

![Screenshot der Registerkarte "Einstellungen" für die App "Lob"](media/manage-praise-app-settings.png)

> [!NOTE]
> Das Feature der App "Lob" steht in den Wolken der US-Regierung nicht zur Verfügung.

## <a name="use-built-in-badge-sets"></a>Verwenden von integrierten Signalsätzen

Integrierte Gruppen sind Sammlungen von Signalen, die von Microsoft für die App "Lob" entworfen wurden. Diese Gruppen können von Administratoren nicht bearbeitet werden. Der Standardabzeichensatz ist bereits aktiviert und in der App "Lob" verfügbar. Um die Verfügbarkeit des Standardsatzs oder von Signalsätzen zu ändern, setzen Sie den entsprechenden Umschalter auf "Ein" oder "Aus". 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>Standardabzeichen

Der Standardabzeichensatz soll Teams Benutzern dabei helfen, ihre Kollegen zu erkennen, damit sie mit ihrer Arbeit über- und darüber hinaus gehen können.

![Vorschau auf den Standardabzeichensatz](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>Soziale und emotionale Lernabzeichen für Bildungseinrichtungen

Lehrkräfte können einzelne Schüler/Studenten für soziales und emotionales Lernen (SEL) mit Signalen erkennen, die diese Konzepte veranschaulichen.

![Vorschau auf die Sozialen und emotionalen Lernabzeichen für Bildungseinrichtungen](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>Erstellen eigener Badges

Wählen Sie **"Benutzerdefiniertes Signal erstellen" aus.** Von hier aus können Sie im Seitenbereich ein benutzerdefiniertes Signal entwerfen. Sie können bis zu 25 benutzerdefinierte Badges erstellen. 

![Screenshot des Bereichs "Benutzerdefiniertes Signal erstellen"](media/manage-praise-app-create-custom-badge.png)

1. Geben Sie einen Signalnamen ein. Dies ist der Name, der im Signal angezeigt wird, wenn Benutzer Lob senden.

2. Legen Sie die Signalfarben festgelegt. Zum Festlegen der Text- und Hintergrundfarben ihres Badges müssen Sie die Farben als hexadezimale Werte (hexadezimal) eingeben.

   > [!TIP]
   > Wenn Sie mit Hexadezimalwerten noch [](#hex-colors-intro) nicht so genau zu erfahren sind, enthält dieser Artikel eine kurze Einführung, in der Sie erfahren, wie sie verwendet werden.

3. Laden Sie ein Signalbild hoch. Der akzeptierte Dateityp ist . PNG. Die Bilddatei muss kleiner als 40 KB sein und maximal 216 x 216 Pixel groß sein.
![Signal mit Beschriftung für Hintergrund-, Text- und Bildfelder](media/praise-app-badge-fields.png)

4. Name des Badges lokalisieren: Wählen Sie unter **"Lokalisierte Signalnamen"** die Option **"Hinzufügen" aus.** Wählen Sie das gewünschte Locale aus der Dropdownliste aus. Geben Sie dann den Signalnamen in der festgelegten Sprache ein.

5. Schließen Sie Ihr Signal aus bestimmten Locales aus: Wählen Sie unter "Signal von diesen **Locales** ausschließen" die Option **"Hinzufügen" aus.** Wählen Sie die Locales aus, die Sie aus der Dropdownliste ausschließen möchten.

6. Wählen Sie **"Übernehmen"** aus. Ihr neues Signal wird jetzt in der benutzerdefinierten Tabelle mit Signalen angezeigt.

> [!NOTE]
> Wenn die Schritte 4 und 5 übersprungen werden, wird das Signal in der Standardsprache für alle Locales angezeigt.
>
> Wenn Sie alle Änderungen an Ihrer Signalauswahl vorgenommen haben, stellen Sie sicher, dass "Absenden" **ausgewählt ist.** Es kann einige Stunden dauern, bis diese Änderungen für Ihre Organisation zur Verfügung stehen.

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>Angeben von Farben mit Hexadezimalwerten

Hexadezimalfarbwerte sind Zeichenfolgen mit sechs hexadezimalen Ziffern, die die Intensität von Rot (RR), Grün (GG) und Blau (BB) in einer bestimmten Farbe bei einer Skalierung von 00 bis FF darstellen. Wenn Sie die Werte aller drei Farben zusammenbringen, erhalten Sie einen Hexadezimalwert: #RRGGBB

Beispielsweise ist der Hexadezimalwert für die Farbe Rot #FF0000 da Rot auf den höchsten möglichen Wert festgelegt wird, FF sowie Grün und Blau jeweils auf den niedrigsten möglichen Wert , 00, festgelegt.

Unterschiedliche Farben und deren Hexadezimalwerte erhalten Sie in [der Bing-Farbauswahl.](https://www.bing.com/search?q=color+picker)

Im Folgenden finden Sie eine Liste mit Beispielfarben für die ersten Schritte:

|Farbe  |Hexadezimalwert|
|-------|---------|
|![Hexadezimalfarbenfarbe #FF6666](media/hexColor1.png)|  #FF6666   |
|![Hexadezimalfarbe #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![hexadezimal #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![Hexadezimalfarbe #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![Hexadezimalfarbe #800080](media/hexColor5.png)|  #800080   |
|![Hexadezimalfarbe #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>Bewährte Methoden zum Erstellen von benutzerdefinierten Signalen

**Senden Sie alle Badges auf einmal.** Da es eine Weile dauert, bis neue Badges verarbeitet werden, sollten Sie am besten alle benutzerdefinierten Badges zur Tabelle hinzufügen, bevor Sie sie übermitteln.

**Berücksichtigen Sie bei der Auswahl von Farben die Barrierefreiheit.** Einige Farben sind besser zusammen als andere.  Erstellen Sie Kontrast zwischen Text und Hintergrundfarben, damit der Signalname leichter zu lesen ist. Wenn Sie beispielsweise eine dunkle Hintergrundfarbe ausgewählt haben, wählen Sie eine helle Textfarbe aus.

**Beachten Sie beim Auswählen eines Bilds die Signalabmessungen.** Für eine optimale Qualität wird empfohlen, eine Bilddatei mit einer Größe von 216 x 216 Pixel hochzuladen (dies sind die maximalen Abmessungen). Vermeiden Sie es, das Bild zu dehnen oder zu verfälschen, damit es in diese Abmessungen passt.

**Wenn das Signalbild nicht rechteckig ist, machen Sie das Bild transparent.** Sie müssen dies tun, bevor Sie die Bilddatei in Lob hochladen.

![Links: Signal mit nicht transparentem Bild, rechts: Signal mit transparentem Bild](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>Ressourcen für Signalsatz

Integrierte Signalsätze können nicht geändert werden. Wenn also ein integrierter Satz aktiviert ist, werden alle Badges im Satz der App "Lob" hinzugefügt. Wenn Sie bestimmte Badges aus einem integrierten Satz hinzufügen und andere badges weg lassen möchten, erstellen Sie die Badges, die Sie als benutzerdefinierte Badges verwenden möchten, erneut. Sie können das Signalbild herunterladen und den Text und die Hintergrundfarben von Signalen aus den integrierten Gruppen in den folgenden Tabellen suchen.

### <a name="default-badges-assets"></a>Standardressourcen für Badges

</br>

|Signalname     |Bilddatei  |Textfarbe | Hintergrundfarbe |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|Prima        |[Fantastisches PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|Trainer          |[Coach PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|Abt.        |[Courage PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|Kreativ       |[Creative PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|Inklusiv      |[Inklusives PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|Kind Heart     |[Kind Heart PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|Leadership     |[Leadership PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Abt.       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|Problemlöser |[Problemlöser PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|Teamplayer    |[Teamplayer PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|Danke      |[Vielen Dank! PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>Soziale und emotionale Lernabzeichen für Bildungsressourcen

</br>

|Signalname        |Bilddatei  |Textfarbe | Hintergrundfarbe |
|------------------|------------|---------- |--------|
|Kommunikation     |[Kommunikation PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|Kritisches Denken |[Kritisches Denken PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|Kurios         |[Png für die Heiterheit](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|Einfühlungsvermögen           |[Einfühlungsvermögen PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|Zielstrebung      |[Ziel ist png](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|Motivation        |[Motivation PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|Persistenz       |[Persistenz PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|Respekt           |[Png respektieren](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|Verantwortlichkeit    |[Verantwortung PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|Selbsterklingung    |[Selbsterklingung PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|Selbstverwaltung   |[Selbstverwaltung PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thought überdacht    |[Thought verfeineren PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
