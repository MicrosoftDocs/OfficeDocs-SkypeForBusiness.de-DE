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
description: 'Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration ausführen, wenn Sie Folgendes in Ihrer älteren Umgebung angepasst haben:'
ms.openlocfilehash: 19ff3b0ca389832cfb2b1739aeb85738c30238576143d3542388fd1ef97a6498
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306218"
---
# <a name="migrate-address-book"></a>Migrieren des Adressbuchs

Im Allgemeinen wird das Adressbuch zusammen mit der restlichen Topologie migriert. Möglicherweise müssen Sie jedoch einige Schritte nach der Migration ausführen, wenn Sie Folgendes in Ihrer älteren Umgebung angepasst haben: 

- Sie haben die Normalisierungsregeln für das Adressbuch angepasst.

- Sie haben den Standardwert für den **UseNormalizationRules**-Parameter in "False" geändert. 


 **Adressbuch-Normalisierungsregeln**

Wenn Sie in Ihrer älteren Umgebung Adressbuchnormalisierungsregeln angepasst haben, müssen Sie die angepassten Regeln zu Ihrem Pilotpool migrieren. Haben Sie die Adressbuch-Normalisierungsregeln nicht angepasst, ist für den Adressbuchdienst nichts zu migrieren. Die Standardnormalisierungsregeln für Skype for Business Server 2019 sind mit den Standardregeln für die Legacyinstallation identisch. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um angepasste Normalisierungsregeln zu migrieren.

> [!NOTE]
> Wenn in Ihrer Organisation Remoteanrufsteuerung verwendet wird und Sie Normalisierungsregeln für Adressbücher angepasst haben, müssen Sie das Verfahren in diesem Thema ausführen, bevor Sie die Remoteanrufsteuerung nutzen können. Dazu müssen Sie Mitglied der Gruppe "RTCUniversalServerAdmins" sein oder gleichwertige Rechte innehaben. 

 **Festlegen von "UseNormalizationRules" auf "False"**

Wenn Sie den Wert für **UseNormalizationRules** auf "False" festlegen, damit Benutzer Telefonnummern verwenden können, die in Active Directory Domain Services definiert sind, ohne dass Skype for Business Server 2019 Normalisierungsregeln anwenden muss, müssen Sie die Parameter **UseNormalizationRules** und **IgnoreGenericRules** auf "True" festlegen. Führen Sie das später in diesem Abschnitt beschriebene Verfahren aus, um diese Parameter auf "True" festzulegen. 

## <a name="to-migrate-address-book-customized-normalization-rules"></a>So migrieren Sie angepasste Normalisierungsregeln für Adressbücher

1. Suchen Sie die Company_Phone_Number_Normalization_Rules.txt Datei im Stammverzeichnis des freigegebenen Adressbuchordners, und kopieren Sie sie in den Stammordner des freigegebenen Adressbuchordners in Ihrem Skype for Business Server 2019-Pilotpool.

    > [!NOTE]
    > Die Beispiele für die Normalisierungsregeln für Adressbücher wurden in Ihrem ABS Web-Komponentendateiverzeichnis installiert. Der Pfad ist **$installedDriveLetter:\Program Files\Microsoft Skype for Business Server 2019\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt**. Diese Datei kann als **Company_Phone_Number_Normalization_Rules.txt** in das Stammverzeichnis des freigegebenen Adressbuchordners kopiert und umbenannt werden. For example, the address book shared in **$serverX**, the path will be similar to: **\\ $serverX \SkypeForBusiness-FileShare\2-WebServices-1\ABFiles**. 

2. Öffnen Sie die Datei "Company_Phone_Number_Normalization_Rules.txt" in einem Text-Editor, z. B. Editor.

3. Bestimmte Eintragstypen funktionieren in Skype for Business Server 2019 nicht ordnungsgemäß. Durchsuchen Sie die Datei nach den hier beschriebenen Typen von Einträgen, bearbeiten Sie die Einträge entsprechend, und speichern Sie die Änderungen im freigegebenen Adressbuchordner im Pilotpool.

    Zeichenfolgen, die erforderliche Leerzeichen oder Satzzeichen enthalten, können Fehler bei der Ausführung der Normalisierungsregeln verursachen, weil diese Zeichen aus den Zeichenfolgen, die in die Normalisierungsregeln eingelesen werden, entfernt werden. Wenn Sie Zeichenfolgen mit erforderlichen Leerzeichen oder Satzzeichen haben, müssen Sie diese Zeichenfolgen bearbeiten. Beispielsweise würde die folgende Zeichenfolge einen Fehler bei der Normalisierungsregel verursachen:

   ```console
   \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
   ```

    Mit der folgenden Zeichenfolge würde die Normalisierungsregel fehlerfrei ausgeführt werden:

   ```console
   \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d
   ```

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a>So legen Sie "UseNormalizationRules" und "IgnoreGenericRules" auf "True" fest

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Microsoft Skype for Business Server 2019"** und dann auf **Skype for Business Server Verwaltungsshell.**

2. Führen Sie einen der folgenden Schritte aus:

   - Wenn Ihre Bereitstellung nur Skype for Business Server 2019 umfasst, führen Sie das folgende Cmdlet auf globaler Ebene aus, um die Werte für **UseNormalizationRules** und **IgnoreGenericRules** in True zu ändern: 

   ```PowerShell
   Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

   - Wenn Ihre Bereitstellung eine Kombination aus Skype for Business Server 2019 und einer Legacyinstallation enthält, führen Sie das folgende Cmdlet aus, und weisen Sie es jedem Skype for Business Server 2019-Pool in der Topologie zu:

   ```PowerShell
   New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
   ```

3. Warten Sie, bis die Replikation des zentralen Verwaltungsspeichers in allen Pools erfolgt.

4. Ändern Sie die Datei mit den Telefonnormalisierungsregeln ("Company_Phone_Number_Normalization_Rules.txt") für die Bereitstellung, sodass die Inhalte gelöscht werden. Die Datei befindet sich in der Dateifreigabe jedes Skype for Business Server 2019-Pools. Wenn die Datei nicht vorhanden ist, erstellen Sie eine leere Datei mit der Bezeichnung "Company_Phone_Number_Normalization_Rules.txt".

5. Warten Sie einige Minuten, bis alle Front-End-Pools die neuen Dateien gelesen haben.

6. Führen Sie das folgende Cmdlet für jeden Skype for Business Server 2019-Pool in Ihrer Bereitstellung aus:

   ```PowerShell
   Update-CsAddressBook
   ```


