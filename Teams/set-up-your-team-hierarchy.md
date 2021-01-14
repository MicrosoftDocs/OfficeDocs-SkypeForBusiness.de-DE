---
title: Einrichten der Teamzielhierarchie
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Erfahren Sie, wie Sie in Ihrer Organisation eine Teamhierarchie einrichten, um Inhalte in einer großen Gruppe von Teams zu veröffentlichen.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06244553c051677533d275ad6cd47052775d01f7
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865249"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Einrichten der Teamzielhierarchie

Durch das Einrichten einer Teamzielhierarchie kann Ihre Organisation Inhalte in einer großen Gruppe von Teams veröffentlichen. Die Teamzielhierarchie definiert, wie alle Teams in Ihrer Hierarchie miteinander verknüpft sind, welche Benutzer Aufgaben veröffentlichen können und für welche Teams Benutzer Berechtigungen zum Veröffentlichen besitzen. Veröffentlichungsfeatures sind für alle Benutzer deaktiviert, es sei denn, für Ihre Organisation ist eine Teamzielhierarchie eingerichtet. Zum Einrichten einer Teamzielhierarchie müssen Sie eine Datei erstellen, die die Hierarchie definiert, und sie dann in Teams hochladen, um sie auf Ihre Organisation anzuwenden. Nachdem das Schema hochgeladen wurde, kann es von Apps in Teams verwendet werden. Hier können Sie üben, wie Sie eine Hierarchie einrichten und mithilfe eines Skripts in Ihren Teams-Mandanten [hochladen.](https://docs.microsoft.com/microsoftteams/set-up-your-team-hierarchy#Create-a-sample-hierarchy)

> [!IMPORTANT]
> Für die erste Version unterstützt nur die App "Aufgaben" hierarchische Teams.  Das Anwenden einer Teamzielhierarchie auf Ihre Organisation ermöglicht die [Veröffentlichung von](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) Aufgaben in der Aufgaben-App. Es wird keine Hierarchie von Teams in anderen Bereichen von Microsoft Teams angezeigt.

Hier ist ein Beispiel dafür, wie die Hierarchie in der App "Aufgaben" in Teams dargestellt wird. Nachdem eine Aufgabenliste erstellt wurde, können die Mitglieder des Veröffentlichungsteams die Empfängerteams auswählen, an die die Aufgabenliste gesendet (veröffentlicht) werden soll. Bei der Auswahl von Teams kann das Veröffentlichungsteam nach Hierarchie, Nach Attributen oder einer Kombination aus beiden filtern.<br>

![Screenshot der Vorgangsveröffentlichung](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminologie

Die folgenden Begriffe sind beim Navigieren in Hierarchien wichtig. Teams werden als Knoten **bezeichnet.**

* **Stammknoten** sind die obersten Knoten in der Hierarchie. Im Beispiel ist Einzelhandelskommunikation ein Stammknoten.
* **Übergeordnete knoten** und **untergeordnete Knoten** sind Konditionen, die eine Beziehung zwischen zwei verbundenen Knoten darstellen. Im Beispiel ist "Bezirk 01" ein untergeordneter Knoten von Bereich 1.
* Mehrere Ebenen von untergeordneten Elemente werden als **Nachfolgerebenen bezeichnet.** Die Bezirke 01, Store 01, Store 03, Store 07, District 02 und District 03 sind Nachfolger von Flächen 1.
* Ein Knoten ohne kinder wird als **Blattknoten bezeichnet.** Sie befinden sich ganz unten in einer Hierarchie.
* **Empfängerteams** sind Teams, die ausgewählt wurden, um eine bestimmte Gruppe von Inhalten zu erhalten, die veröffentlicht werden sollen. Sie müssen untergeordnete Knoten sein.

## <a name="plan-your-hierarchy"></a>Planen der Hierarchie

Bevor Sie das Schema erstellen, mit dem Ihre Hierarchie definiert wird, müssen Sie eine Planung treffen und entscheiden, wie Sie Ihre Organisation gestalten möchten.  Eine der ersten Prioritäten ist die Entscheidung, welche Organisationsgruppen Aufgaben für andere Gruppen veröffentlichen müssen. Jeder Knoten in der Hierarchie stellt eine Arbeitsgruppe oder Gruppe von Gruppen dar.

### <a name="permissions-to-publish"></a>Berechtigungen zum Veröffentlichen

Die Berechtigung zum Veröffentlichen hängt davon ab, ob ein Benutzer Mitglied einer beliebigen Teams in der Hierarchie sowie die Beziehung dieses Teams oder einer Gruppe von Teams zu anderen Teams in der Hierarchie ist.

> [!NOTE]
> Dem Besitzer eines Teams werden auch Veröffentlichungsberechtigungen erteilt.

* Wenn ein Benutzer ein Mitglied von mindestens einem Team ist, das Nachfolger von Nachfolgern in der Hierarchie hat, kann dieser Benutzer in diesen Nachfolgern veröffentlichen, ohne Mitglied aller Teams zu sein, in denen er veröffentlichen möchte.
* Wenn ein Benutzer Mitglied eines mindestens eines Teams in der Hierarchie ist, aber kein Mitglied eines Teams mit Nachfolgern in der Hierarchie ist, kann dieser Benutzer veröffentlichte Inhalte von seiner Organisation anzeigen und empfangen.
* Wenn ein Benutzer kein Mitglied eines Teams in der Hierarchie ist, werden diesem Benutzer keine Veröffentlichungsfunktionen angezeigt.

### <a name="guidelines"></a>Richtlinien

* Pro Organisation kann nur eine Hierarchiedatei angewendet werden. Sie können jedoch verschiedene Teile Ihrer Organisation als getrennte Hierarchien von Knoten in einer einzigen CSV-Datei zusammenbringen. Contoso Pharmaceuticals verfügt z. B. über einen Stammknoten "Einzelhändler" und einen Stammknoten "Einzelhandel". Beide Stammknoten haben mehrere Zeilen mit Nachfolgern, und es gibt keine Überlappung zwischen ihnen.
* Nur untergeordnete Knoten können Empfänger einer Publikation sein. Andere Knoten in der Hierarchie sind hilfreich beim Auswählen der Empfänger einer Publikation.
* Ein Team kann nur einmal in einer Hierarchie dargestellt werden.
* Eine Hierarchie kann bis zu 15.000 Knoten enthalten. Wir planen die Zusammenarbeit mit Kunden, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example-hierarchy"></a>Beispielhierarchie

In der folgenden Hierarchie können z. B. "Rückruf", "Kommunikation" und "Personalwesen" Aufgaben für jeden untersten Knoten (Team) in der Hierarchie veröffentlichen, "Zone mit "Zone", jedoch können Aufgaben nur in den Teams "New York Store" und "Boston Store" veröffentlicht werden. Die Beispielhierarchie ermöglicht es den Gruppen "Rückruf", "Kommunikation" und "Personalwesen", Aufgaben zu veröffentlichen, die für das gesamte Unternehmen gelten, z. B. Informationen zu Leistungen oder Nachrichten vom CEO. Aufgaben wie Personalplanung, Wetterinformationen und so weiter können nur an teams aus dem New York Store und dem Boston Store veröffentlicht werden.

![Hierarchisches Teambeispiel](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Erstellen der Hierarchie

> [!NOTE]
> Im weiteren Verlauf dieses Artikels wird das Einrichten einer Teamhierarchie im Kontext der Veröffentlichung von Aufgaben an Empfängerteams erläutert. Unter ["Verwalten der App "Aufgaben" für Ihre Organisation in Teams](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) finden Sie eine Übersicht über die Aufgaben-App, in der die Aufgabenveröffentlichung angezeigt wird, wenn sie aktiviert ist.

Das Schema, das die Hierarchie definiert, basiert auf einer Datei mit durch Kommas getrennten Werten (CSV). Jede Zeile in der CSV-Datei entspricht einem Knoten in der Hierarchie von Teams. Jede Zeile enthält Informationen, die den Knoten innerhalb der Hierarchie nennen, ihn optional mit einem Team verknüpft, und enthält Attribute, mit deren Hilfe Teams in Apps gefiltert werden können, die dies unterstützen.

Sie können auch **Buckets** definieren. Dabei handelt es sich um Kategorien, die das Veröffentlichungsteam zum Organisieren von An Empfängerteams verwendet, um ihnen das Anzeigen, Sortieren und Konzentrieren auf relevante Inhalte zu erleichtern.

### <a name="add-required-columns"></a>Hinzufügen erforderlicher Spalten

Die Datei "CSV" muss die folgenden drei Spalten (beginnend bei der ersten Spalte) in der folgenden Reihenfolge enthalten. Ein Knoten muss mit einem Team verknüpft sein, damit er Aufgaben empfangen kann.

| Spaltenname   | Erforderlich | Beschreibung   |
----------------|----------|---------------|
| DisplayName    | Ja      | Dieses Feld ist der Name des Knotens. Der Name kann bis zu 100 Zeichen lang sein und nur die Zeichen A-Z, a-z und 0-9 enthalten. Knotennamen müssen eindeutig sein. |
| ParentName    | Ja       | Dies ist der Name des übergeordneten Knotens. Der hier festgelegte Wert muss exakt mit dem Wert im Feld **"DisplayName"** des übergeordneten Knotens übereinstimmen. Wenn Sie mehrere übergeordnete Knoten hinzufügen möchten, trennen Sie jeden übergeordneten Knotennamen durch ein Semikolon (;). Sie können bis zu 25 übergeordnete Knoten hinzufügen, und jeder Name des übergeordneten Knotens kann bis zu 2.500 Zeichen lang sein. Ein Knoten kann nur dann über mehrere übergeordnete Knoten verfügen, wenn es sich bei den übergeordneten Knoten um Stammknoten handelt.   <br><br>**WICHTIG** Achten Sie darauf, keine Schleife zu erstellen, bei der ein übergeordnetes Element oben in der Hierarchie auf einen untergeordneten Knoten in der Hierarchie verweist. Dies wird nicht unterstützt. |
| TeamId        | Ja, wenn das Team Aufgaben veröffentlicht oder Aufgaben von einem übergeordneten Knoten empfängt       | Sie enthält die ID des Teams, mit dem Sie einen Knoten verknüpfen möchten. Jeder Knoten muss auf ein eindeutiges Team verweisen, damit jeder Wert von "TeamId" nur einmal in der Hierarchiedatei angezeigt werden kann. Führen Sie den folgenden PowerShell-Befehl aus, um die ID eines Teams zu erhalten, mit dem Sie einen Knoten verknüpfen `Get-Team | Export-Csv TeamList.csv` möchten: Dieser Befehl listet die Teams in Ihrer Organisation auf und enthält den Namen und die ID für jedes Team. Suchen Sie den Namen des Teams, zu dem Sie eine Verknüpfung erstellen möchten, und kopieren Sie dann die ID in dieses Feld.|

> [!NOTE]
> Wenn es sich bei einem Knoten nicht um einen Stammknoten oder einen blattigen Knoten handelt und Sie die Teammitgliedschaft nicht benötigen, um die entsprechenden Berechtigungen für die Veröffentlichung und Berichterstellung zu erteilen, können Sie die TeamId leer lassen. Diese Methode kann verwendet werden, um die Granularität beim Auswählen von Empfängerteams oder beim Anzeigen von Abschlussberichten ohne ein entsprechendes Team zu forschen.

### <a name="add-attribute-columns"></a>Hinzufügen von Attributspalten

Nachdem Sie die drei erforderlichen Spalten hinzugefügt haben, können Sie optionale Attributspalten hinzufügen. Diese Attribute können zum Filtern von Knoten verwendet werden, sodass Sie einfacher diejenigen auswählen können, für die Sie Aufgaben veröffentlichen möchten. Es gibt zwei Möglichkeiten zum Definieren der Attribute, je nachdem, ob sich die Werte für dieses Attribut gegenseitig ausschließen.

|Methoden zum Hinzufügen von Attributen|Beschreibung |Beispiel  |
|---|---------|---------|
|Wenn sich die Werte für ein Attribut gegenseitig ausschließen, wird der von Ihnen festgelegte Spaltenname zum Namen des Attributs.|Jede Zeile kann einen Wert für dieses Attribut enthalten, und jede Attributspalte kann bis zu 50 eindeutige Werte enthalten. Jeder Wert kann bis zu 100 Zeichen umfassen. Die Gruppe von Attributwerten, die Sie in der Attributspalte angeben, wird als Filterwerte für dieses Attribut angezeigt, wenn Die Empfängerteams mithilfe der Teamzielhierarchie ausgewählt werden.|Sie möchten, dass Benutzer Speicher nach Layout filtern können. Die Werte für dieses Attribut schließen sich gegenseitig aus, da ein Speicher nur ein Layout haben kann. <br><br>Um ein Attribut zum Filtern von Stores nach Layout hinzuzufügen, fügen Sie eine Spalte mit dem Namen "Store-Layout" hinzu. In diesem Beispiel sind die Werte für das Layoutattribut "Store" "Compact", "Standard" und "Large".
|Wenn Sie mehrere Werte für ein Attribut angeben müssen und sich die Werte nicht gegenseitig ausschließen, verwenden Sie das **Format "AttributeName:UniqueValue"** für die Spaltennamen. <br><br>**WICHTIG** Verwenden Sie unbedingt den englischen Doppelpunkt (:) da Unicode nicht als Attributspaltentrennzeichen unterstützt wird. |Die Textzeichenfolge vor dem Doppelpunkt (:) wird der Name des Attributs. Alle Spalten mit derselben Textzeichenfolge vor den Doppelpunkt (:) werden zu einem Abschnitt im Filtermenü gruppieren. Jede Zeichenfolge nach dem Doppelpunkt wird zu den Werten für diesen Abschnitt.<br><br>Jede Zeile kann für dieses Attribut den Wert 0 (Null) oder 1 haben. Der Wert 0 bedeutet, dass das Attribut nicht auf den Knoten angewendet wird, und der Wert 1 bedeutet, dass das Attribut auf diesen Knoten angewendet wird.|Sie möchten, dass Benutzer Stores nach Abteilung filtern können. Ein Speicher kann mehrere Abteilungen haben, sodass sich die Werte für dieses Attribut nicht gegenseitig ausschließen.<br><br>In diesem Beispiel fügen wir "Departments:Clothing", "Departments:Electronic", "Departments:Food", "Departments:Home and Garden", "Departments:Sports Goods" als Attributspalten hinzu. Abteilungen werden zum Attributnamen, und Benutzer können nach den Abteilungen "Bekleidung", "Elektronik", "Lebensmittel", "Home and Garden" und "Sports Goods" filtern.|

Beachten Sie beim Hinzufügen einer Attributspalte Folgendes:

* Der Spaltenname, den Sie angeben, oder der Spaltenname, den Sie vor dem Doppelpunkt (:) wird der Name des Attributs. Dieser Wert wird in den Teams-Apps angezeigt, die die Hierarchie verwenden.
* Die Hierarchie kann bis zu 50 Attributspalten enthalten.
* Der Spaltenname darf bis zu 100 Zeichen umfassen und enthält nur die Zeichen A-Z, a-z und 0-9 sowie Leerzeichen. Spaltennamen müssen eindeutig sein.

### <a name="add-bucket-columns"></a>Hinzufügen von Bucketspalten

Sie können Bucketspalten hinzufügen, um Buckets zu erstellen, bei denen es sich um Gruppierungen handelt, in denen Aufgaben organisiert werden können. Jeder Bucket erhält eine eigene Spalte in der CSV-Datei. Die buckets, die Sie erstellen, werden dem Veröffentlichungsteam zur Verfügung stehen. Das Veröffentlichungsteam kann dann diese Buckets verwenden, um Aufgaben für die Empfängerteams zu kategorisieren. Wenn ein Bucket in einem Team noch nicht vorhanden ist, werden Buckets bei der Veröffentlichung von Aufgaben bei Bedarf erstellt.

Durch die zentrale Kategorisierung der Arbeitsaufgaben kann das Veröffentlichungsteam die Aufgabenliste für alle Zehner-, Hunderter- oder Tausende von Empfängerteams, die die Aufgabenliste erhalten, vorab organisieren. Die Empfängerteams können dann ihre Aufgaben nach Bucket sortieren und filtern, um sich auf den bereich zu konzentrieren, der für ihre Arbeit am relevantesten ist.

Wenn Sie eine Bucketspalte hinzufügen, beachten Sie Folgendes:

* Der Spaltenname wird zum Namen des Buckets. Jeder von Ihnen festgelegte Bucket wird in der Bucketliste in den Teams-Apps angezeigt, die die Hierarchie verwenden.
* Es wird empfohlen, keine vertraulichen Informationen in Bucketnamen zu verwenden. Derzeit können Veröffentlichungsteams einen Bucket nach seiner Veröffentlichung nicht durch Veröffentlichen entfernen.
* Dem Spaltennamen muss ein Hashtag (#) vorangehen. Er darf bis zu 100 Zeichen umfassen und nur die Zeichen A-Z, a-z und 0-9 enthalten. Beispiel: #Operations und #Frozen Waren"
* Eine Hierarchie kann bis zu 25 Bucketspalten enthalten. Wir planen die Zusammenarbeit mit Kunden, um diesen Grenzwert für größere Organisationen zu erhöhen.

### <a name="example"></a>Beispiel

Hier sehen Sie ein Beispiel für eine CSV-Schemadatei, die zur Unterstützung der in der vorherigen Abbildung gezeigten Hierarchie erstellt würde. Dieses Schema enthält Folgendes:

* Drei erforderliche Spalten mit dem `TargetName` Namen `ParentName` , und `TeamId`
* Drei Attributspalten mit dem `Store layout` `Departments:Clothing` Namen , und `Departments:Foods`
* Drei Bucketspalten mit `Fresh Foods` dem `Frozen Foods` Namen ", und" `Women's Wear`

Das `Store layout` Attribut enthält Werte wie "," und `Compact` `Standard` "." `Large` Die `Departments` Attributspalten können auf einen Wert von `0` (Null) oder festgelegt `1` werden. Das `Store` Layout und die Attribute werden in der Abbildung oben nicht `Departments` angezeigt. Sie werden hier hinzugefügt, um zu zeigen, wie Knoteneinträgen Attribute hinzugefügt werden können. Dasselbe gilt für die drei Bucketspalten.

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a>Anwenden der Hierarchie

Nachdem Sie Ihre Hierarchie in der Schema-CSV-Datei definiert haben, können Sie sie in Teams hochladen. Führen Sie dazu den folgenden Befehl aus. Sie müssen ein globaler Administrator oder ein Teams-Dienstadministrator sein, um diesen Schritt zu unternehmen.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Aktualisieren der Hierarchie

Sie können eine neue Hierarchie hochladen, um die alte Hierarchie mit demselben Befehl wie oben zu ersetzen. Jedes Mal, wenn Sie eine neue Hierarchie hochladen, ersetzt sie die vorherige Hierarchie.

### <a name="check-the-status-of-your-hierarchy"></a>Überprüfen des Status der Hierarchie

Sie können den folgenden Befehl ausführen, um den Status des Hierarchieuploads zu überprüfen.

```powershell
Get-TeamTargetingHierarchyStatus
```

Der Befehl gibt die folgenden Felder zurück:

Feld|Beschreibung
-----|------------
ID | Die eindeutige ID für den Upload.
Status | Uploadstatus. Zu den Werten **gehören "Starting",** **"Validating",** **"Successful"** und **"Failed".**
ErrorDetails | Details, wenn ein Uploadfehler auftritt. Weitere Informationen zu den Fehlerdetails finden Sie im Abschnitt zur Problembehandlung. Wenn kein Fehler auftritt, ist dieses Feld leer.
LastUpdatedAt | Zeitstempel und Datum, an dem die Datei zuletzt aktualisiert wurde.
LastModifiedBy | Die ID des letzten Benutzers, der die Datei geändert hat.
FileName | Der Dateiname der CSV.

## <a name="remove-your-hierarchy"></a>Entfernen der Hierarchie

Wenn Sie die Registerkarte  "Veröffentlichte Listen" für alle Benutzer in Ihrer Organisation sofort deaktivieren möchten, können Sie die Hierarchie entfernen. Die Benutzer haben keinen Zugriff auf die **Registerkarte** "Veröffentlichte Listen" oder eine der Funktionen auf der Registerkarte.  Dies umfasst die Möglichkeit zum Erstellen neuer Aufgabenlisten zum Veröffentlichen, Zugreifen auf Entwurfslisten, Veröffentlichen, Aufheben der Veröffentlichung und Duplizieren von Listen sowie zum Anzeigen von Berichten. Durch das Entfernen der Hierarchie wird die Veröffentlichung von Vorgängen, die zuvor veröffentlicht wurden, nicht wieder aufheben. Diese Aufgaben bleiben für die Empfängerteams verfügbar.

Führen Sie zum Entfernen der Hierarchie den folgenden Befehl aus. Sie müssen ein Administrator sein, um diesen Schritt ausführen zu können.

```powershell
Remove-TeamTargetingHierarchy
```

Beim Bestätigen des Löschvorgangs wird in der Statusmeldung weiterhin angezeigt, dass das vorherige Schema vorhanden ist, obwohl beim erneuten Löschen ein Fehler zurückgegeben wird, dass das Objekt null ist.

## <a name="create-a-sample-hierarchy"></a>Erstellen einer Beispielhierarchie

### <a name="install-the-teams-powershell-module"></a>Installieren des Teams -PowerShell-Moduls

> [!IMPORTANT]
> Um diesen Schritt ausführen zu können, müssen Sie das Teams PowerShell Public Preview-Modul aus dem [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Gallery installieren und verwenden. Schritte zum Installieren des Moduls finden Sie unter ["Installieren von Teams PowerShell".](teams-powershell-install.md)

### <a name="sample-script"></a>Beispielskript

Das folgende Skript kann verwendet werden, um die Teams zu erstellen und eine CSV-Datei in Ihren Microsoft Teams-Mandanten hochzuladen. Wenn bereits eine Hierarchie vorhanden ist, wird sie durch dieses Skript ersetzt.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Erstellen von Teams für eine einfache Hierarchie

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Verwenden von Teamdaten zum Erstellen einer durch Kommas getrennten Ausgabe (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Speichern der Ausgabe in einer CSV-Datei im **Ordner "Downloads"**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Hochladen der Hierarchie

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="how-to-view-error-details"></a>So wird's machen: Anzeigen von Fehlerdetails

Sie können den folgenden Befehl ausführen, um zu verstehen, was einen Fehler verursacht, und die Fehlerdetails zurückzukehren.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

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

* [Verwalten der App "Aufgaben" für Ihre Organisation in Teams](manage-tasks-app.md)
* [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
