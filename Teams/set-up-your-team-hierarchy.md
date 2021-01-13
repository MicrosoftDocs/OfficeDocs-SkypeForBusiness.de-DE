---
title: Einrichten der Teamzielhierarchie
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Erfahren Sie, wie Sie in Ihrer Organisation eine Teamhierarchie einrichten, um Inhalte in einer großen Gruppe von Teams zu veröffentlichen.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099ee82e5890e81b6fc89a5ffc1842d936e6ad1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806155"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Einrichten der Teamzielhierarchie

> **Dieses Feature befindet sich derzeit in einer privaten Vorschau.**

Um eine Hierarchie von Teams zu erstellen, die von Ihrer Organisation zum Veröffentlichen von Inhalten in einer großen Gruppe von Teams verwendet werden kann, müssen Sie Ihr Schema für Teamzielierung einrichten. Das Schema definiert, wie alle Teams in Ihrer Hierarchie miteinander in Beziehung stehen und welche Attribute zum Filtern Ihrer Teams verwendet werden können. Nachdem Sie das Schema erstellt haben, laden Sie es in Teams hoch, und die Hierarchie wird in der gesamten Organisation angewendet. Nachdem das Schema hochgeladen wurde, können die Apps im Teamclient es verwenden. 

> [!IMPORTANT]
> Beim Durchsuchen von Teams oder Kanälen innerhalb dieser Teams wird keine Hierarchie angezeigt. Um die Hierarchie von Teams zu sehen, müssen Sie eine App verwenden, die sie unterstützt. Für die erste Version unterstützt nur die App "Aufgaben" hierarchische Teams. Im weiteren Verlauf dieses Artikels wird das Einrichten einer Teamhierarchie im Kontext der Veröffentlichung von Aufgaben an Empfängerteams erläutert. Bevor Sie ihre Teamzielhierarchie einrichten, finden Sie unter "Verwalten der App ["Aufgaben" für](manage-tasks-app.md) Ihre Organisation in Teams eine Übersicht über die Veröffentlichung von Aufgaben.

Hier ist ein Beispiel dafür, wie die Hierarchie in der App "Aufgaben" in Teams dargestellt wird. Nachdem eine Aufgabenliste erstellt wurde, können die Mitglieder des Veröffentlichungsteams die Empfängerteams auswählen, an die die Aufgabenliste gesendet (veröffentlicht) werden soll. Bei der Auswahl von Teams kann das Veröffentlichungsteam nach Hierarchie, Nach Attributen oder einer Kombination aus beiden filtern.<br>

![Screenshot der Vorgangsveröffentlichung](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planen der Hierarchie

Bevor Sie das Schema erstellen, mit dem Ihre Hierarchie definiert wird, müssen Sie eine Planung treffen und entscheiden, wie Sie Ihre Organisation gestalten möchten. Dazu gehört auch die Entscheidung, welche Organisationsgruppen Aufgaben für andere Gruppen veröffentlichen müssen. Jeder Knoten in der Hierarchie stellt eine Arbeitsgruppe oder Gruppe von Gruppen dar. Knoten am Unteren Rand der Hierarchie (diejenigen ohne untergeordnete Knoten) sind Teams, die Aufgaben empfangen können, während andere Knoten (Eltern) Organisationsgruppen mit der Berechtigung zum Veröffentlichen von Vorgängen nach unten sind. Ein Team kann nur einmal in der Hierarchie dargestellt werden.

In der folgenden Hierarchie können z. B. "Rückruf", "Einzelhandelskommunikation" und "Personalwesen" Aufgaben für jeden untersten Knoten (Team) in der Hierarchie veröffentlichen, während aufgaben in der Zone "Nord-Ost" nur in den Teams des New York Store und des Boston Store veröffentlicht werden können. Diese Hierarchie ermöglicht es den Gruppen "Rückruf", "Einzelhandelskommunikation" und "Personalwesen", Aufgaben zu veröffentlichen, die für das gesamte Unternehmen gelten, z. B. Informationen zu Leistungen oder Nachrichten vom CEO. Die Zone "Nord-Ost" kann Vorgänge wie die Personalplanung, Wetterinformationen und vieles mehr nur für die Teams aus dem New York Store und dem Boston Store veröffentlichen.

![Hierarchisches Teambeispiel](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Erstellen der Hierarchie

Das Schema, das die Hierarchie definiert, basiert auf einer Datei mit durch Kommas getrennten Werten (CSV). Jede Zeile in der CSV-Datei entspricht einem Knoten in der Hierarchie von Teams. Jede Zeile enthält Informationen, die den Knoten innerhalb der Hierarchie nennen, ihn optional mit einem Team verknüpft, und enthält Attribute, mit deren Hilfe Teams in Apps gefiltert werden können, die dies unterstützen.

Sie können auch Buckets definieren, bei denen es sich um Kategorien handelt, die das Veröffentlichungsteam zum Organisieren von An Empfängerteams gesendeten Inhalten verwenden kann, um ihnen das Anzeigen, Sortieren und Konzentrieren auf relevante Inhalte zu erleichtern.

### <a name="add-required-columns"></a>Hinzufügen erforderlicher Spalten

Die Datei "CSV" muss die folgenden drei Spalten (beginnend bei der ersten Spalte) in der folgenden Reihenfolge enthalten. Ein Knoten muss mit einem Team verknüpft sein, damit er Aufgaben empfangen kann. Während der privaten Vorschau werden 2.000 Knoten unterstützt. Beim Start wird standardmäßig mindestens 15.000 Knoten unterstützt. Wir planen die Zusammenarbeit mit Kunden, um diesen Grenzwert für größere Organisationen zu erhöhen.

| Spaltenname   | Erforderlich | Beschreibung   |
----------------|----------|---------------|
| TargetName    | Ja      | Dies ist der Name des Knotens. Der Name kann bis zu 100 Zeichen lang sein und nur die Zeichen A-Z, a-z und 0-9 enthalten. Knotennamen müssen eindeutig sein. |
| ParentName    | Ja       | Dies ist der Name des übergeordneten Knotens. Der wert, den Sie hier angeben, muss exakt mit dem Wert im Feld "TargetName" des übergeordneten Knotens übereinstimmen. Wenn Sie mehrere übergeordnete Knoten hinzufügen möchten, trennen Sie jeden übergeordneten Knotennamen durch ein Semikolon (;). Sie können bis zu 25 übergeordnete Knoten hinzufügen, und jeder Name des übergeordneten Knotens kann bis zu 2.500 Zeichen lang sein. Ein Knoten kann nur dann über mehrere übergeordnete Knoten verfügen, wenn es sich bei den übergeordneten Knoten um Stammknoten handelt.   <br><br>**WICHTIG** Achten Sie darauf, keine Schleife zu erstellen, bei der ein übergeordnetes Element oben in der Hierarchie auf einen untergeordneten Knoten in der Hierarchie verweist. Dies wird nicht unterstützt. |
| TeamId        | Ja, wenn das Team Aufgaben veröffentlicht oder Aufgaben von einem übergeordneten Knoten empfängt       | Sie enthält die ID des Teams, mit dem Sie einen Knoten verknüpfen möchten. Ein Knoten muss mit einem Team verknüpft sein, wenn er sich am unteren Rand der Hierarchie befindet, Sie möchten, dass Benutzer über diesen Knoten veröffentlichen können oder wenn Sie möchten, dass Benutzer Berichte für diesen Knoten und seine Nachfolger von diesem Knoten anzeigen können. Wenn Ihr Vorgesetzter für das Office für die Region "Westen" z. B. berichte zum Abschluss der Aufgabe für die Knoten sehen möchte, die zu dieser Region gehören.<br><br>Wenn Sie einen Knoten nur zum Zweck der Gruppierung anderer Knoten in der Hierarchie hinzufügen möchten, müssen Sie diesen Knoten nicht mit einem Team verknüpfen und können dieses Feld leer lassen. Sie können jeden Knoten nur mit einem Team verknüpfen.<br>Führen Sie den folgenden PowerShell-Befehl aus, um die ID eines Teams zu erhalten, mit dem Sie einen Knoten verknüpfen `Get-Team | Export-Csv TeamList.csv` möchten: Hier werden die Teams in Ihrer Organisation aufgeführt und der Name und die ID für jedes Team aufgeführt. Suchen Sie den Namen des Teams, zu dem Sie eine Verknüpfung erstellen möchten, und kopieren Sie dann die ID in dieses Feld.|

### <a name="add-attribute-columns"></a>Hinzufügen von Attributspalten

Nachdem Sie die drei erforderlichen Spalten hinzugefügt haben, können Sie optionale Attributspalten hinzufügen. Diese Attribute können zum Filtern von Knoten verwendet werden, sodass Sie einfacher diejenigen auswählen können, für die Sie Aufgaben veröffentlichen möchten. Es gibt zwei Möglichkeiten zum Definieren der Attribute, je nachdem, ob sich die Werte für dieses Attribut gegenseitig ausschließen.

|Methoden zum Hinzufügen von Attributen|Beschreibung |Beispiel  |
|---|---------|---------|
|Wenn sich die Werte für ein Attribut gegenseitig ausschließen, wird der von Ihnen festgelegte Spaltenname zum Namen des Attributs.|Jede Zeile kann einen Wert für dieses Attribut enthalten, und jeder Wert kann bis zu 100 Zeichen lang sein. Die Gruppe von Attributwerten, die Sie in der Attributspalte angeben, wird als verfügbare Filterwerte für dieses Attribut in Teams-Apps angezeigt, die die Hierarchie verwenden. Jede Attributspalte kann bis zu 50 eindeutige Werte haben. |Sie möchten, dass Benutzer Speicher nach Layout filtern können. Die Werte für dieses Attribut schließen sich gegenseitig aus, da ein Speicher nur ein Layout haben kann. <br><br>Um ein Attribut zum Filtern von Stores nach Layout hinzuzufügen, fügen Sie eine Spalte mit dem Namen "Store-Layout" hinzu. In diesem Beispiel sind die Werte für das Layoutattribut "Store" "Compact", "Standard" und "Large".
|Wenn Sie mehrere Werte für ein Attribut angeben müssen und sich die Werte nicht gegenseitig ausschließen, verwenden Sie das **Format "AttributeName:UniqueValue"** für die Spaltennamen. |Die Textzeichenfolge vor dem Doppelpunkt (:) wird der Name des Attributs. Alle Spalten, die dieselbe Textzeichenfolge vor dem Doppelpunkt (:) werden zu einem Abschnitt im Filtermenü gruppieren. Jede Zeichenfolge nach dem Doppelpunkt wird zu den Werten für diesen Abschnitt.<br><br>Jede Zeile kann für dieses Attribut den Wert 0 (Null) oder 1 haben. Der Wert 0 bedeutet, dass das Attribut nicht auf den Knoten angewendet wird, und der Wert 1 bedeutet, dass das Attribut auf diesen Knoten angewendet wird.|Sie möchten, dass Benutzer Stores nach Abteilung filtern können. Ein Speicher kann mehrere Abteilungen haben, sodass sich die Werte für dieses Attribut nicht gegenseitig ausschließen.<br><br>In diesem Beispiel fügen wir "Departments:Clothing", "Departments:Electronic", "Departments:Food", "Departments:Home and Garden", "Departments:Sports Goods" als Attributspalten hinzu. Abteilungen werden zum Attributnamen, und Benutzer können nach den Abteilungen "Bekleidung", "Elektronik", "Lebensmittel", "Home and Garden" und "Sports Goods" filtern.|

Beachten Sie beim Hinzufügen einer Attributspalte Folgendes:

- Der Spaltenname, den Sie angeben, oder der Spaltenname, den Sie vor dem Doppelpunkt (:) wird der Name des Attributs. Dieser Wert wird in den Teams-Apps angezeigt, die die Hierarchie verwenden.
- Der Spaltenname darf bis zu 100 Zeichen umfassen und enthält nur die Zeichen A-Z, a-z und 0-9 sowie Leerzeichen. Spaltennamen müssen eindeutig sein.
- Beim Start sind 50 Attributspalten geplant.

### <a name="add-bucket-columns"></a>Hinzufügen von Bucketspalten

Sie können Bucketspalten hinzufügen, um Buckets zu erstellen, bei denen es sich um Gruppierungen handelt, in denen Aufgaben organisiert werden können. Jeder Bucket erhält eine eigene Spalte in der CSV-Datei. Die buckets, die Sie erstellen, werden dem Veröffentlichungsteam zur Verfügung stehen. Das Veröffentlichungsteam kann dann diese Buckets verwenden, um Aufgaben für die Empfängerteams zu kategorisieren. Wenn ein Bucket in einem Team noch nicht vorhanden ist, werden Buckets bei der Veröffentlichung von Aufgaben bei Bedarf erstellt.

Durch die zentrale Kategorisierung der Arbeit kann das Veröffentlichungsteam die Aufgabenliste für alle Zehner-, Hunderter- oder Tausende von Empfängerteams, die die Aufgabenliste erhalten, vorab organisieren. Die Empfängerteams können dann ihre Aufgaben nach Bucket sortieren und filtern, um sich auf den bereich zu konzentrieren, der für ihre Arbeit am relevantesten ist.

Wenn Sie eine Bucketspalte hinzufügen, beachten Sie Folgendes:

- Der Spaltenname wird zum Namen des Buckets. Jeder von Ihnen festgelegte Bucket wird in der Bucketliste in den Teams-Apps angezeigt, die die Hierarchie verwenden. Es wird empfohlen, keine vertraulichen Informationen in Bucketnamen zu verwenden. Derzeit können Veröffentlichungsteams einen Bucket nach seiner Veröffentlichung nicht durch Veröffentlichen entfernen.
- Dem Spaltennamen muss ein Hashtag (#) vorangehen. Er darf bis zu 100 Zeichen umfassen und nur die Zeichen A-Z, a-z und 0-9 enthalten. Beispiel: #Operations und #Frozen Waren"
- Beim Start erwarten wir, dass 25 Bucketspalten unterstützt werden. Wir planen die Zusammenarbeit mit Kunden, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example"></a>Beispiel

Hier sehen Sie ein Beispiel für eine CSV-Schemadatei, die erstellt würde, um die in der Abbildung oben gezeigte Hierarchie zu unterstützen. Dieses Schema enthält Folgendes:

- Drei erforderliche Spalten mit dem `TargetName` Namen `ParentName` , und `TeamId`
- Drei Attributspalten mit dem `Store layout` `Departments:Clothing` Namen , und `Departments:Foods`
- Drei Bucketspalten mit `Fresh Foods` dem `Frozen Foods` Namen ", und" `Womenswear`

Das `Store layout` Attribut enthält Werte wie "," und `Compact` `Standard` "." `Large` Die `Departments` Attributspalten können auf einen Wert von `0` (Null) oder festgelegt `1` werden. Das `Store` Layout und die Attribute werden in der Abbildung oben nicht `Departments` angezeigt. Sie werden hier hinzugefügt, um zu zeigen, wie Knoteneinträgen Attribute hinzugefügt werden können. Dasselbe gilt für die drei Bucketspalten.


| TargetName             | ParentName                      | TeamId                       | Layout "Store"|Abteilungen:Bekleidung|Abteilungen:Lebensmittel|#Fresh Lebensmittel|#Frozen Lebensmittel|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Rückruf                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Kommunikation         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Regionales Büro Ost   |                         |                                      |||||||
| Regionales Büro West   |                         |                                      |||||||
| Zone im Osten des Ostens        | Regionales Büro Ost    |                                      |||||||
| Südostzone        | Regionales Büro Ost    |                                      |||||||
| New York Store         | Zone im Osten des Ostens         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Groß|1|1||||
| Speicher in Boston           | Zone im Osten des Ostens         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Der Store für 2010            | Südostzone         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Kompakt|0|1||||
| New Int.-Store      | Südostzone         | 6be960b8-72af-4561-a343-9ac4711874eb |Kompakt|0|1||||
| Seattle Store          | Regionales Büro West    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Los Angeles Store      | Regionales Büro West    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Groß|1|1||||

## <a name="apply-your-hierarchy"></a>Anwenden der Hierarchie

> [!IMPORTANT]
> Um diesen Schritt ausführen zu können, müssen Sie das Teams PowerShell Public Preview-Modul aus dem [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Gallery installieren und verwenden. Schritte zum Installieren des Moduls finden Sie unter ["Installieren von Teams PowerShell".](teams-powershell-install.md)

Nachdem Sie Ihre Hierarchie in der Schema-CSV-Datei definiert haben, können Sie sie in Teams hochladen. Führen Sie dazu den folgenden Befehl aus. Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um diesen Schritt ausführen zu können.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Entfernen der Hierarchie

> [!IMPORTANT]
> Um diesen Schritt ausführen zu können, müssen Sie das Teams PowerShell Public Preview-Modul aus dem [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Gallery installieren und verwenden. Schritte zum Installieren des Moduls finden Sie unter ["Installieren von Teams PowerShell".](teams-powershell-install.md)

Wenn Sie die Registerkarte  "Veröffentlichte Listen" für alle Benutzer in Ihrer Organisation sofort deaktivieren möchten, können Sie die Hierarchie entfernen. Die Benutzer haben keinen Zugriff auf die **Registerkarte** "Veröffentlichte Listen" oder eine der Funktionen auf der Registerkarte.  Dies umfasst die Möglichkeit zum Erstellen neuer Aufgabenlisten zum Veröffentlichen, Zugreifen auf Entwurfslisten, Veröffentlichen, Aufheben der Veröffentlichung und Duplizieren von Listen sowie zum Anzeigen von Berichten. Durch das Entfernen der Hierarchie wird die Veröffentlichung von Vorgängen, die zuvor veröffentlicht wurden, nicht wieder aufheben. Diese Aufgaben bleiben für die Empfängerteams verfügbar. 

Führen Sie zum Entfernen der Hierarchie den folgenden Befehl aus. Sie müssen ein Administrator sein, um diesen Schritt ausführen zu können. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Beim Hochladen der Schema-CSV-Datei wird eine Fehlermeldung angezeigt

Notieren Sie sich die Fehlermeldung, da sie Informationen zur Problembehandlung enthalten sollte, um anzugeben, warum das Schema nicht hochgeladen werden konnte. Überprüfen und bearbeiten Sie Ihre Schema-CSV-Datei basierend auf den Informationen in der Fehlermeldung, und versuchen Sie es dann erneut.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Beim Hochladen der Schema-CSV-Datei wird die Fehlermeldung "Fehler: InvalidTeamId" angezeigt.

Wenn Sie versuchen, Ihre Schema-CSV-Datei hochzuladen, wird die folgende Fehlermeldung angezeigt:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Stellen Sie sicher, dass Sie die richtige Team-ID für das Team in Ihrer Schema-CSV-Datei verwenden. Die TeamId sollte mit der Gruppen-ID der Microsoft 365-Gruppe identisch sein, die das Team unterstützt. Sie können die Gruppen-ID des Teams im Microsoft Teams Admin Center nachschauen. 

1. Wechseln Sie in der linken Navigationsleiste des [Microsoft Teams Admin Centers](https://admin.teams.microsoft.com/)zu **"Teams**  >  **verwalten".**
2. Wenn die **Spalte "Gruppen-ID"** in der Tabelle nicht angezeigt wird, wählen Sie **"Spalten** bearbeiten" in der oberen rechten Ecke der Tabelle aus, und aktivieren Sie dann **"Gruppen-ID".**
3. Suchen Sie das Team in der Liste, und suchen Sie dann die Gruppen-ID.

Stellen Sie sicher, dass die TeamId in Ihrer Schema-CSV-Datei der Gruppen-ID entspricht, die im Microsoft Teams Admin Center angezeigt wird. 

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der App "Aufgaben" für Ihre Organisation in Teams](manage-tasks-app.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
