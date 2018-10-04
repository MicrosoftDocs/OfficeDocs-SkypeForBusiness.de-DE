---
title: Migrieren von Adressbüchern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert. Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst:'
ms.openlocfilehash: 01279284086499b112028644ea0e1ca2fc708dd0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370769"
---
# <a name="migrate-address-book"></a>Migrieren von Adressbüchern

Im Allgemeinen wird zusammen mit dem Rest der Topologie im Adressbuch migriert. Sie müssen jedoch möglicherweise einige Schritte nach der Migration ausführen, wenn Sie die folgenden in der Vorversion Umgebung angepasst: 

- Legen Sie die WMI-Eigenschaft **PartitionbyOU** auf Adressbucheinträge nach Organisationseinheit (OU). 

- Die Adressbuch-Normalisierungsregeln angepasst.

- Der Standardwert für den **UseNormalizationRules** -Parameter auf "false" geändert. 

  **Gruppierte Adressbucheinträge**

Wenn Sie die **"partitionbyou"** WMI-Eigenschaft auf True, um das Erstellen von Adressbüchern für jede Organisationseinheit festlegen, müssen Sie das **"MsRTCSIP-groupingid"** Active Directory-Attribut für Benutzer und Kontakte festgelegt, wenn Gruppieren von Adressbucheinträgen fortgesetzt werden soll. Zum Gruppe Adressbucheinträgen sollten zum Einschränken des Bereichs der Adressbuch-Suchvorgänge. Schreiben Sie mithilfe des Attributs **"MsRTCSIP-groupingid"** , ein Skript zum Füllen Sie des Attributs, das Zuweisen von den gleichen Wert für alle Benutzer, die Sie gruppieren möchten. Weisen Sie beispielsweise einen single-Wert für alle Benutzer in einer Organisationseinheit. 

 **Beheben von Adressbuch-Normalisierungsregeln**

Wenn Sie in Ihrer Umgebung legacy-Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die benutzerdefinierten Regeln zum pilotpool migrieren. Wenn Ihnen nicht Adressbuch-Normalisierungsregeln konfiguriert, müssen Sie nichts für Adressbuchdienst migrieren. Die Standard-Normalisierungsregeln für Skype für Business Server 2019 stimmen die Regeln für die legacy-Installation. Führen Sie die weiter unten in diesem Abschnitt, um angepasste Normalisierungsregeln migrieren.

> [!NOTE]
> Wenn Ihre Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln Adressbuch angepasst, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie Remoteanrufsteuerung verwenden können. Das Verfahren ist die Mitgliedschaft in der Gruppe RTCUniversalServerAdmins oder über vergleichbare Rechte erforderlich. 

 **UseNormalizationRules "false" festgelegt**

Wenn den Wert für **UseNormalizationRules** auf False festgelegt werden, sodass Benutzer Rufnummern verwenden können, wie sie in definiert sind, Active Directory Domain Services, ohne dass Skype für Business Server 2019 anwenden Normalisierungsregeln, müssen Sie die **festlegen UseNormalizationRules** und **IgnoreGenericRules** -Parameter auf "true". Führen Sie die weiter unten in diesem Abschnitt können Sie diesen Parameter auf True festgelegt. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>Informationen zum Adressbuch migrieren Sie angepasste Normalisierungsregeln für

1. Suchen Sie die Datei Company_Phone_Number_Normalization_Rules.txt im Stamm des freigegebenen adressbuchordners, und kopieren Sie sie in den Stamm des freigegebenen adressbuchordners in Ihrer Skype für Business Server 2019 pilot Pool.

    > [!NOTE]
    > Die Beispiel-Adressbuch-Normalisierungsregeln wurden in Ihrem ABS Web Component Dateiverzeichnis installiert. Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype für Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Diese Datei kann kopiert und als **Company_Phone_Number_Normalization_Rules.txt** in Address Book des freigegebenen Ordners Stammverzeichnis umbenannt werden. Beispielsweise in **$serverX**freigegebenen Adressbuch der Pfad werden ähnelt: ** \\$serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Verwenden Sie einen Text-Editor wie Editor ein, um die Datei Company_Phone_Number_Normalization_Rules.txt zu öffnen.

3. Bestimmte Arten von Einträgen funktioniert ordnungsgemäß in Skype für Business Server 2019 nicht. Suchen Sie in der Datei für die Arten von Einträgen in diesem Schritt beschriebene, bearbeiten Sie diese nach Bedarf, und Speichern der Änderungen an der freigegebenen adressbuchordners im pilotpool.

    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen Ursache Normalisierungsregeln ein Fehler auftritt, da diese Zeichen aus der Zeichenfolge entfernt werden, die Eingabe ist, die Normalisierungsregeln enthalten. Wenn Sie Zeichenfolgen, die erforderlichen Leerzeichen oder Satzzeichen enthalten verfügen, müssen Sie die Zeichenfolgen ändern. Beispielsweise würde die folgende Zeichenfolge die Normalisierungsregel fehlerfrei ausgeführt:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt nicht:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>UseNormalizationRules und IgnoreGenericRules auf "true" festlegen

1. Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype für Business Server 2019**, und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.

2. Wählen Sie eine der folgenden Optionen aus:

   - Wenn Ihre Bereitstellung nur Skype für Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern: 

   ```
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Wenn Ihre Bereitstellung eine Kombination von Skype für Business Server 2019 und eine legacy-Installation umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype für Business Server 2019 Pool in der Topologie:

   ```
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Warten Sie zentralen Speicher Replikation für alle Pools erfolgt.

4. Ändern Sie die rufnummernnormalisierung Regeldatei "Company_Phone_Number_Normalization_Rules.txt" für die Bereitstellung den Inhalt gelöscht. Die Datei befindet sich auf die Dateifreigabe jedes Skype für Business Server 2019 Pool. Wenn die Datei nicht vorhanden ist, klicken Sie dann erstellen Sie eine leere Datei mit dem Namen "Company_Phone_Number_Normalization_Rules.txt".

5. Warten Sie einige Minuten für alle Front-End-Pools die neuen Dateien gelesen.

6. Führen Sie das folgende Cmdlet auf jede Skype für Business Server 2019 Pool in Ihrer Bereitstellung aus:

   ```
   Update-CsAddressBook
   ```


