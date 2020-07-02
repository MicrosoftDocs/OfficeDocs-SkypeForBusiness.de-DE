---
title: Einrichten Ihrer Zielgruppen Adressierungs Hierarchie
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Hier erfahren Sie, wie Sie eine Team Hierarchie in Ihrer Organisation einrichten, um Inhalte in einer Vielzahl von Teams zu veröffentlichen.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 136b06a6c134fc2ec906c8c2175d462f71a5b9a6
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944018"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Einrichten Ihrer Zielgruppen Adressierungs Hierarchie

> **Diese Funktion befindet sich derzeit in der privaten Vorschau.**

Wenn Sie eine Hierarchie von Teams erstellen möchten, die von Ihrer Organisation zum Veröffentlichen von Inhalten in einer Vielzahl von Teams verwendet werden kann, müssen Sie das Zielgruppen Adressierungsschema einrichten. Das Schema definiert, wie alle Teams in der Hierarchie miteinander verbunden sind, und die Attribute, die zum Filtern Ihrer Teams verwendet werden können. Nachdem Sie das Schema erstellt haben, laden Sie es in Teams hoch, und die Hierarchie wird in Ihrer Organisation angewendet. Nachdem das Schema hochgeladen wurde, kann es von apps innerhalb des Teams-Clients verwendet werden. 

> [!IMPORTANT]
> Eine Hierarchie von Teams wird nicht angezeigt, wenn Sie innerhalb von Teams oder Kanälen suchen. Wenn Sie die Hierarchie von Teams anzeigen möchten, müssen Sie eine APP verwenden, die Sie unterstützt. Für die erste Version unterstützt nur die Aufgaben-app hierarchische Teams. Im weiteren Verlauf dieses Artikels wird erläutert, wie Sie eine Team Hierarchie im Kontext von Veröffentlichungsaufgaben für Empfänger Teams einrichten. Bevor Sie Ihre Zielgruppen Adressierungs Hierarchie einrichten, lesen Sie [Verwalten der Aufgaben-app für Ihre Organisation in Teams](manage-tasks-app.md) , um einen Überblick über die Aufgaben Veröffentlichung zu erhalten.

Im folgenden finden Sie ein Beispiel dafür, wie die Hierarchie in der Aufgaben-app in Teams dargestellt wird. Nachdem eine Aufgabenliste erstellt wurde, können Mitglieder des Veröffentlichungsteams die Empfänger Teams auswählen, an die Sie die Aufgabenliste senden (veröffentlichen) möchten. Beim Auswählen von Teams kann das Veröffentlichungsteam nach Hierarchie, nach Attributen oder nach einer Kombination aus beidem filtern.<br>

![Screenshot der Aufgaben Veröffentlichung](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planen Ihrer Hierarchie

Bevor Sie das Schema erstellen, in dem Ihre Hierarchie definiert ist, müssen Sie etwas planen und entscheiden, wie Sie Ihre Organisation gestalten möchten. Dies umfasst die Entscheidung, welche Organisationsgruppen Aufgaben in anderen Gruppen veröffentlichen müssen. Jeder Knoten in der Hierarchie stellt eine Arbeitsgruppe oder Gruppe von Gruppen dar. Knoten am unteren Rand der Hierarchie (ohne untergeordnete Elemente) sind Teams, die Aufgaben empfangen können, während andere Knoten (übergeordnete Elemente) Organisationsgruppen mit der Berechtigung zum nach unten Veröffentlichen von Aufgaben sind. Ein Team kann nur einmal in der Hierarchie dargestellt werden.

In der folgenden Hierarchiekönnen Rückruf, Einzelhandels Kommunikation und HR beispielsweise Aufgaben in jedem untersten Knoten (Team) in der Hierarchie veröffentlichen, während die Nordost Zone nur Aufgaben im New Yorker Store und in Boston Store Teams veröffentlichen kann. Diese Hierarchie ermöglicht es dem Rückruf, der Einzelhandels Kommunikation und den personalgruppen, Aufgaben zu veröffentlichen, die für das gesamte Unternehmen gelten, wie etwa Leistungen oder Nachrichten des CEO. In der Nordost Zone können Aufgaben wie Personalplanung, Wetterinformationen usw. nur im New Yorker Store-und Boston Store-Team veröffentlicht werden.

![Beispiel für eine Team Hierarchie](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Erstellen Ihrer Hierarchie

Das Schema, das Ihre Hierarchie definiert, basiert auf einer CSV-Datei (Comma-Separated Values). Jede Zeile in der CSV-Datei entspricht einem Knoten innerhalb der Hierarchie von Teams. Jede Zeile enthält Informationen, mit denen der Knoten in der Hierarchie benannt, optional mit einem Team verknüpft wird, und enthält Attribute, die verwendet werden können, um Teams in apps zu filtern, die Sie unterstützen.

Sie können auch Buckets definieren, wobei es sich um Kategorien handelt, die vom Veröffentlichungsteam zum Organisieren von Inhalten verwendet werden können, die an Empfänger Teams gesendet werden, um Ihnen das anzeigen, Sortieren und fokussieren auf relevante Inhalte zu erleichtern.

### <a name="add-required-columns"></a>Hinzufügen von erforderlichen Spalten

Die CSV-Datei muss die folgenden drei Spalten in der folgenden Reihenfolge enthalten, beginnend bei der ersten Spalte. Ein Knoten muss mit einem Team verknüpft sein, damit er Aufgaben empfängt. Während der privaten Vorschau unterstützen wir 500-Knoten. Wir erwarten, dass beim Start standardmäßig mindestens 2.000-Knoten unterstützt werden. Wir planen, mit Kunden zusammenzuarbeiten, um diese Grenze für größere Organisationen zu erhöhen.

| Spaltenname   | Erforderlich | Beschreibung   |
----------------|----------|---------------|
| TargetName    | Ja      | Dies ist der Name des Knotens. Der Name kann bis zu 100 Zeichen lang sein und nur die Zeichen a-z, a-z und 0-9 enthalten. Knotennamen müssen eindeutig sein. |
| ParentName    | Ja       | Dies ist der Name des übergeordneten Knotens. Der hier angegebene Wert muss dem Wert im Feld TargetName des übergeordneten Knotens genau entsprechen. Wenn Sie mehr als einen übergeordneten Knoten hinzufügen möchten, trennen Sie die einzelnen übergeordneten Knotennamen durch ein Semikolon (;). Sie können bis zu 25 übergeordnete Knoten hinzufügen, und jeder übergeordnete Knotenname kann bis zu 2500 Zeichen lang sein. Ein Knoten kann nur dann über mehrere übergeordnete Knoten verfügen, wenn die übergeordneten Knoten Stammknoten sind.   <br><br>**Wichtig** Achten Sie darauf, keine Schleife zu erstellen, bei der ein übergeordnetes übergeordnetes Element in der Hierarchie auf einen untergeordneten Knoten in der Hierarchie verweist. Dies wird nicht unterstützt. |
| Team-Nr        | Ja, wenn das Team Aufgaben veröffentlicht oder Aufgaben von einem übergeordneten Knoten empfängt       | Diese enthält die ID des Teams, mit dem ein Knoten verknüpft werden soll. Ein Knoten muss mit einem Team verknüpft sein, wenn er sich unten in der Hierarchie befindet, wenn Sie möchten, dass die Benutzer von diesem Knoten aus veröffentlichen können, oder wenn Sie möchten, dass die Benutzer Berichte für diesen Knoten und seine Nachfolger anzeigen können. Wenn Ihr Vorgesetzter für die West Region Office beispielsweise die Berichterstellung zum Abschluss der Aufgabe für die Knoten anzeigen möchte, die zu dieser Region gehören.<br><br>Wenn Sie einen Knoten nur zum Gruppieren anderer Knoten in der Hierarchie hinzufügen möchten, müssen Sie diesen Knoten nicht mit einem Team verknüpfen und können dieses Feld leer lassen. Sie können jeden Knoten mit nur einem Team verknüpfen.<br>Führen Sie den folgenden PowerShell-Befehl aus, um die ID eines Teams abzurufen, mit dem Sie einen Knoten verknüpfen `Get-Team | Export-Csv TeamList.csv` möchten: Damit werden die Teams in Ihrer Organisation aufgelistet und der Name und die ID für die einzelnen Teams eingeschlossen. Suchen Sie den Namen des Teams, mit dem Sie eine Verknüpfung herstellen möchten, und kopieren Sie dann die ID in dieses Feld.|

### <a name="add-attribute-columns"></a>Hinzufügen von Attributspalten

Nachdem Sie die drei erforderlichen Spalten hinzugefügt haben, können Sie optionale Attributspalten hinzufügen. Diese Attribute können verwendet werden, um Knoten zu filtern, sodass Sie die Aufgaben, die Sie veröffentlichen möchten, einfacher auswählen können. Es gibt zwei Möglichkeiten, ihre Attribute zu definieren, je nachdem, ob sich die Werte für dieses Attribut gegenseitig ausschließen.

|Möglichkeiten zum Hinzufügen von Attributen|Beschreibung |Beispiel  |
|---|---------|---------|
|Wenn sich die Werte für ein Attribut gegenseitig ausschließen, wird der von Ihnen angegebene Spaltenname zum Namen des Attributs.|Jede Zeile kann einen Wert für dieses Attribut enthalten, und jeder Wert kann bis zu 100 Zeichen lang sein. Der Satz von Attributwerten, die Sie in der Attributspalte angeben, wird als verfügbare Filterwerte für dieses Attribut in Teams-apps angezeigt, die die Hierarchie verwenden. Jede Attributspalte kann bis zu 50 eindeutige Werte aufweisen. |Sie möchten, dass Benutzerspeicher nach Layout filtern können. Die Werte für dieses Attribut schließen sich gegenseitig aus, da ein Speicher nur ein Layout aufweisen kann. <br><br>Wenn Sie ein Attribut zum Filtern von speichern nach Layout hinzufügen möchten, fügen Sie eine Spalte mit dem Namen Store Layout hinzu. In diesem Beispiel sind Werte für das Store-Layout-Attribut kompakt, Standard und groß.
|Wenn Sie mehrere Werte für ein Attribut angeben müssen und sich die Werte nicht gegenseitig ausschließen, verwenden Sie das Format **attributeName: UniqueValue** für die Spaltennamen. |Die Textzeichenfolge vor dem Doppelpunkt (:) wird zum Namen des Attributs. Alle Spalten, die die gleiche Textzeichenfolge vor dem Doppelpunkt enthalten (:) sind in einem Abschnitt im Menü "filtern" zusammengefasst. Jede der Zeichenfolgen nach dem Doppelpunkt wird zu den Werten für diesen Abschnitt.<br><br>Jede Zeile kann den Wert 0 (null) oder 1 für dieses Attribut aufweisen. Der Wert 0 bedeutet, dass das Attribut nicht auf den Knoten angewendet wird, und der Wert 1 bedeutet, dass das Attribut auf diesen Knoten angewendet wird.|Sie möchten, dass Benutzer Geschäfte nach Abteilungen filtern können. Ein Store kann mehrere Abteilungen aufweisen, sodass sich die Werte für dieses Attribut nicht gegenseitig ausschließen.<br><br>In diesem Beispiel fügen wir Abteilungen hinzu: Kleidung, Abteilungen: Elektronik, Abteilungen: Lebensmittel, Abteilungen: Haus und Garten, Abteilungen: Sportartikel als Attributspalten. Abteilungen werden zum Attributnamen, und Benutzer können nach den Abteilungen Kleidung, Elektronik, Lebensmittel, Haus und Garten sowie Sportartikel filtern.|

Wenn Sie eine Attributspalte hinzufügen, beachten Sie Folgendes:

- Der von Ihnen angegebene Spaltenname oder der Spaltenname, den Sie vor dem Doppelpunkt angeben (:) wird zum Namen des Attributs. Dieser Wert wird in den Teams-apps angezeigt, die die Hierarchie verwenden.
- Der Spaltenname kann bis zu 100 Zeichen lang sein und nur die Zeichen a-z, a-z und 0-9 sowie Leerzeichen enthalten. Spaltennamen müssen eindeutig sein.
- Beim Start planen wir das Zulassen von 50-Attributspalten.

### <a name="add-bucket-columns"></a>Hinzufügen von Bucket-Spalten

Sie können Bucket-Spalten hinzufügen, um Buckets zu erstellen, bei denen es sich um Gruppierungen handelt, in denen Aufgaben organisiert werden können. Jeder Bucket erhält eine eigene Spalte in der CSV-Datei. Die von Ihnen erstellten Buckets werden dem Veröffentlichungsteam zur Verfügung gestellt. Das Veröffentlichungsteam kann dann mithilfe dieser Buckets Aufgaben für die Empfänger Teams kategorisieren. Wenn ein Bucket nicht bereits in einem Team vorhanden ist, werden Buckets bei Bedarf erstellt, wenn Aufgaben veröffentlicht werden.

Durch eine zentrale Kategorisierung der Arbeit kann das Veröffentlichungsteam die Aufgabenliste für alle Zehner, Hunderte oder Tausende von Empfänger Teams vororganisieren, die die Aufgabenliste erhalten. Die Empfänger Teams können Ihre Aufgaben dann nach Bucket sortieren und Filtern, um sich auf den Bereich zu konzentrieren, der für Ihre Arbeit am relevantesten ist.

Wenn Sie eine Bucket-Spalte hinzufügen, beachten Sie Folgendes:

- Der Spaltenname wird zum Namen des Buckets. Jeder Bucket, den Sie angeben, wird in der Buckets-Liste in den Teams-apps angezeigt, die die Hierarchie verwenden. Wir empfehlen, keine vertraulichen Informationen in Bucket-Namen einzubeziehen. Zu diesem Zeitpunkt können Veröffentlichungsteams nach der Erstellung keinen Bucket durch Veröffentlichung entfernen.
- Dem Spaltennamen muss ein hashtag (#) vorangestellt werden. Es kann bis zu 100 Zeichen lang sein und nur die Zeichen a-z, a-z und 0-9 enthalten. Beispielsweise #Operations und #Frozen waren.
- Beim Start erwarten wir, dass 25 Bucket-Spalten unterstützt werden. Wir planen, mit Kunden zusammenzuarbeiten, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example"></a>Beispiel

Nachfolgend finden Sie ein Beispiel für eine CSV-Schemadatei, die zur Unterstützung der Hierarchie in der obigen Abbildung erstellt wird. Dieses Schema enthält Folgendes:

- Drei erforderliche Spalten mit dem Namen " `TargetName` `ParentName` und"`TeamId`
- Drei Attributspalten mit dem Namen " `Store layout` `Departments:Clothing` und"`Departments:Foods`
- Drei Bucket-Spalten mit dem Namen " `Fresh Foods` `Frozen Foods` und"`Womenswear`

Das `Store layout` Attribut enthält Werte, die "und" enthalten `Compact` `Standard` `Large` . Die `Departments` Attributspalten können auf den Wert `0` (null) oder gesetzt werden `1` . Das `Store` Layout und die `Departments` Attribute werden in der obigen Abbildung nicht angezeigt. Sie werden hier hinzugefügt, um zu zeigen, wie Attribute zu Knoten Einträgen hinzugefügt werden können. Das gleiche gilt für die drei Bucket-Spalten.


| TargetName             | ParentName                      | Team-Nr                       | Store-Layout|Abteilungen: Kleidung|Abteilungen: Lebensmittel|#Fresh Foods|#Frozen Foods|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Zurückrufen                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Kommunikation         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| HR                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| East Regional Office   |                         |                                      |||||||
| West Regional Office   |                         |                                      |||||||
| Nordöstliche Zone        | East Regional Office    |                                      |||||||
| South East Zone        | East Regional Office    |                                      |||||||
| New York Store         | Nordöstliche Zone         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Groß|1|1||||
| Boston Store           | Nordöstliche Zone         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Miami Store            | South East Zone         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Compact|0|1||||
| New Orleans-Store      | South East Zone         | 6be960b8-72af-4561-a343-9ac4711874eb |Compact|0|1||||
| Seattle-Store          | West Regional Office    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Los Angeles-Store      | West Regional Office    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Groß|1|1||||

## <a name="apply-your-hierarchy"></a>Anwenden Ihrer Hierarchie

> [!IMPORTANT]
> Um diesen Schritt ausführen zu können, müssen Sie das Public Preview-Modul von Teams PowerShell im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/)installieren und verwenden. Eine schrittweise Anleitung zum Installieren des Moduls finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).

Nachdem Sie Ihre Hierarchie in der CSV-Schemadatei definiert haben, können Sie Sie in Teams hochladen. Führen Sie dazu den folgenden Befehl aus. Sie müssen ein globaler Administrator oder Team Dienstadministrator sein, um diesen Schritt ausführen zu können.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Entfernen Ihrer Hierarchie

> [!IMPORTANT]
> Um diesen Schritt ausführen zu können, müssen Sie das Public Preview-Modul von Teams PowerShell im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams/)installieren und verwenden. Eine schrittweise Anleitung zum Installieren des Moduls finden Sie unter [Installieren von Teams PowerShell](teams-powershell-install.md).

Wenn Sie die Registerkarte " **veröffentlichte Listen** " für alle Benutzer in Ihrer Organisation sofort deaktivieren möchten, können Sie Ihre Hierarchie entfernen. Benutzer haben keinen Zugriff auf die Registerkarte **veröffentlichte Listen** oder auf eine der Funktionen auf der Registerkarte.  Dies umfasst die Möglichkeit zum Erstellen neuer Aufgabenlisten zum Veröffentlichen, zugreifen auf Entwurfs Listen, veröffentlichen, Aufheben der Veröffentlichung und Duplizieren von Listen sowie zum Anzeigen der Berichterstellung. Beim Entfernen der Hierarchie werden Aufgaben, die zuvor veröffentlicht wurden, nicht unveröffentlicht. Diese Aufgaben stehen weiterhin für Empfänger Teams zur Verfügung. 

Führen Sie den folgenden Befehl aus, um Ihre Hierarchie zu entfernen. Sie müssen ein Administrator sein, um diesen Schritt ausführen zu können. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>Beim Hochladen der Schemadatei wird eine Fehlermeldung angezeigt

Notieren Sie sich die Fehlermeldung, da Sie Informationen zur Problembehandlung enthalten sollte, um anzugeben, warum das Schema nicht hochgeladen werden konnte. Überprüfen und bearbeiten Sie Ihre Schema-CSV-Datei auf der Grundlage der Informationen in der Fehlermeldung, und versuchen Sie es dann erneut.

## <a name="related-topics"></a>Verwandte Themen

- [Verwalten der Aufgaben-app für Ihre Organisation in Microsoft Teams](manage-tasks-app.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
