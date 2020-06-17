---
title: Migrieren des Adressbuchs
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer Vorgänger Umgebung angepasst haben:'
ms.openlocfilehash: 6d2ccf0d38814d149495518a71f888f0c2999d24
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752837"
---
# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration durchführen, wenn Sie Folgendes in ihrer Vorgänger Umgebung angepasst haben: 

- Sie haben die Normalisierungsregeln für das Adressbuch angepasst.

- Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert. 


 **Adressbuch-Normalisierungsregeln**

Wenn Sie die Regeln für die Adressbuch Normalisierung in ihrer Vorgänger Umgebung angepasst haben, müssen Sie die benutzerdefinierten Regeln in Ihren Pilot Pool migrieren. Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren. Die Standard Normalisierungsregeln für Skype for Business Server 2019 sind identisch mit den Standardregeln für die Legacy Installation. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.

> [!NOTE]
> If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control. The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights. 

 **Festlegen von "UseNormalizationRules" auf "False"**

Wenn Sie den Wert für **UseNormalizationRules** auf false festlegen, damit Benutzer Telefonnummern so verwenden können, wie Sie in Active Directory-Domänendienste definiert sind, ohne Skype for Business Server 2019 Normalisierungsregeln anzuwenden, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf true festlegen. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>So migrieren Sie angepasste Normalisierungsregeln für Adressbücher

1. Suchen Sie die Company_Phone_Number_Normalization_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuch Ordners, und kopieren Sie Sie in den Stamm des freigegebenen Adressbuch Ordners in Ihrem Skype for Business Server 2019-Pilot Pool.

    > [!NOTE]
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad ist **$installedDriveLetter: \Programme\Microsoft Skype for Business Server 2019 \ Components\Address Adress Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Diese Datei kann kopiert und als **Company_Phone_Number_Normalization_Rules.txt** in das Stammverzeichnis des freigegebenen Adressbuch Ordners umbenannt werden. Beispielsweise ist das in **$serverX**freigegebene Adressbuch der Pfad ähnlich wie: ** \\ $serverX \SkypeForBusiness-FileShare\2-Webservices-1\ABFiles**. 

2. Öffnen Sie die Datei "Company_Phone_Number_Normalization_Rules.txt" in einem Text-Editor, z. B. Editor.

3. Bestimmte Arten von Einträgen funktionieren in Skype for Business Server 2019 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.

    Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules. If you have strings that include required whitespace or punctuation, you need to modify the strings. For example, the following string would cause the normalization rule to fail:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft Skype for Business Server 2019**, und klicken Sie dann auf **Skype for Business Server Management Shell**.

2. Führen Sie einen der folgenden Schritte aus:

   - Wenn Ihre Bereitstellung nur Skype for Business Server 2019 enthält, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in true zu ändern: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Wenn Ihre Bereitstellung eine Kombination aus Skype for Business Server 2019 und einer Legacy Installation enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Pool Skype for Business Server 2019 in der Topologie zu:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools ausgeführt wird.

4. Ändern Sie die Datei mit den Telefonnormalisierungsregeln ("Company_Phone_Number_Normalization_Rules.txt") für die Bereitstellung, sodass die Inhalte gelöscht werden. Die Datei befindet sich in der Dateifreigabe jedes Skype for Business Server 2019-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit der Bezeichnung "Company_Phone_Number_Normalization_Rules.txt".

5. Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6. Führen Sie das folgende Cmdlet für jeden Skype for Business Server 2019-Pool in der Bereitstellung aus:

   ```PowerShell
   Update-CsAddressBook
   ```


