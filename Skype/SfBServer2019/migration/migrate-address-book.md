---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer Legacyumgebung angepasst haben:'
ms.openlocfilehash: 8c8e66a8182890ee6e3673769ddc620bb04404c6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40990100"
---
# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie die folgenden Schritte in ihrer Legacyumgebung angepasst haben: 

- Benutzerdefinierte Adressbuch-Normalisierungsregeln.

- Der Standardwert für den **UseNormalizationRules** -Parameter wurde auf "false" geändert. 


 **Regeln für die Normalisierung des Adressbuchs**

Wenn Sie in ihrer Legacyumgebung Adressbuch-Normalisierungsregeln angepasst haben, müssen Sie die angepassten Regeln in Ihren Pilot Pool migrieren. Wenn Sie die Regeln für die Adressbuch Normalisierung nicht angepasst haben, müssen Sie für den Adressbuchdienst nichts migrieren. Die standardmäßigen Normalisierungsregeln für Skype for Business Server 2019 sind mit den Standardregeln für die Legacy Installation identisch. Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um angepasste Normalisierungsregeln zu migrieren.

> [!NOTE]
> Wenn in Ihrer Organisation die Remoteanrufsteuerung verwendet wird und Sie die Regeln für die Adressbuch Normalisierung angepasst haben, müssen Sie das in diesem Thema beschriebene Verfahren ausführen, bevor Sie die Remoteanrufsteuerung verwenden können. Für das Verfahren ist die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe oder entsprechende Rechte erforderlich. 

 **UseNormalizationRules auf "false" festgelegt**

Wenn Sie den Wert für **UseNormalizationRules** auf "false" festlegen, damit Benutzer Telefonnummern verwenden können, wie Sie in Active Directory-Domänendiensten definiert sind, ohne dass Skype for Business Server 2019 Normalisierungsregeln anwenden, müssen Sie die **UseNormalizationRules** -und **IgnoreGenericRules** -Parameter auf "true" festlegen. Führen Sie die Schritte weiter unten in diesem Abschnitt aus, um diese Parameter auf "true" festzulegen. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>So migrieren Sie Adressbuch angepasste Normalisierungsregeln

1. Suchen Sie die Datei "Company_Phone_Number_Normalization_Rules. txt" im Stammverzeichnis des freigegebenen Ordners "Adressbuch", und kopieren Sie Sie in den Stammordner des freigegebenen Adressbuch Ordners in Ihrem Skype for Business Server 2019-Pilot Pool.

    > [!NOTE]
    > Das Beispiel für die Normalisierungsregeln für das Adressbuch wurde im Dateiverzeichnis der ABS-Webkomponente installiert. Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype for Business Server 2019 \ Web Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt**. Diese Datei kann als **Company_Phone_Number_Normalization_Rules. txt** in das Stammverzeichnis des freigegebenen Ordners des Adressbuchs kopiert und umbenannt werden. Beispielsweise ist das in **$serverX**freigegebene Adressbuch der Pfad ähnlich wie: ** \\$serverX \SkypeForBusiness-FileShare\2-Webservices-1\ABFiles**. 

2. Verwenden Sie einen Text-Editor wie Editor, um die Datei "Company_Phone_Number_Normalization_Rules. txt" zu öffnen.

3. Bestimmte Arten von Einträgen funktionieren in Skype for Business Server 2019 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den in diesem Schritt beschriebenen Arten von Einträgen, bearbeiten Sie Sie nach Bedarf, und speichern Sie die Änderungen im freigegebenen Ordner des Adressbuchs in Ihrem Pilot Pool.

    Zeichenfolgen, die erforderliche leer-oder Interpunktionszeichen enthalten, führen zu Normalisierungsregeln, da diese Zeichen aus der Zeichenfolge entfernt werden, die für die Normalisierungsregeln eingegeben wurde. Wenn Zeichenfolgen vorhanden sind, die die erforderlichen Leerzeichen oder Interpunktionszeichen enthalten, müssen Sie die Zeichenfolgen ändern. Die folgende Zeichenfolge würde beispielsweise dazu führen, dass die Normalisierungsregel fehlschlägt:

   ```
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    Die folgende Zeichenfolge würde nicht dazu führen, dass die Normalisierungsregel fehlschlägt:

   ```
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>So setzen Sie UseNormalizationRules und IgnoreGenericRules auf "true"

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.

2. Führen Sie einen der folgenden Schritte aus:

   - Wenn Ihre Bereitstellung nur Skype for Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** auf "true" zu ändern: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Wenn Ihre Bereitstellung eine Kombination aus Skype for Business Server 2019 und einer Legacy Installation umfasst, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype for Business Server 2019-Pool in der Topologie zu:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.

4. Ändern Sie die Regeldatei für die Telefon Normalisierung, "Company_Phone_Number_Normalization_Rules. txt", für Ihre Bereitstellung, um den Inhalt zu löschen. Die Datei befindet sich auf der Dateifreigabe jedes Skype for Business Server 2019-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit dem Namen "Company_Phone_Number_Normalization_Rules. txt".

5. Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6. Führen Sie das folgende Cmdlet für jeden Skype for Business Server 2019-Pool in Ihrer Bereitstellung aus:

   ```PowerShell
   Update-CsAddressBook
   ```


