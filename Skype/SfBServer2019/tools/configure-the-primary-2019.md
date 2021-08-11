---
title: Konfigurieren des primären Verwaltungsservers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2019.'
ms.openlocfilehash: 2606c87d5874bdec4e6dded494b024bc7810de70db000c2c65892e0d80e5a6d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277530"
---
# <a name="configure-the-primary-management-server"></a>Konfigurieren des primären Verwaltungsservers

**Zusammenfassung:** Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2019.

Um die neuen Funktionen für die Integritätsüberwachung in Skype for Business Server 2019 voll nutzen zu können, müssen Sie zunächst einen Computer als primären Verwaltungsserver festlegen. Anschließend müssen Sie System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 auf diesem Computer installieren. Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server installieren, um als Ihre Operations Manager-Back-End-Datenbank zu funktionieren.

Wenn Sie System Center Operations Manager installieren, müssen Sie alle Komponenten dieses Produkts installieren, einschließlich:

- Betriebsdatenbank

- Server

- Konsole

- Windows PowerShell-Cmdlets

- Webkonsole

- Berichterstellung

- Data Warehouse

> [!IMPORTANT]
> Das "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" muss installiert werden, bevor Sie System Center Operations Manager 2012 installieren.

Ausführliche Informationen zu diesen Produkten und deren Installation finden Sie unter den folgenden Links:

- [System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))

- [System Center Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Beachten Sie, dass Pro Skype for Business Server Bereitstellung nur ein Stammverwaltungsserver vorhanden sein kann.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importieren der Skype for Business Server 2019 Management Packs

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann, wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst und gemeldet werden sollen. Skype for Business Server 2019 umfasst zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:

- **Das Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) verfolgt Skype for Business Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Kommunikationsdatensätzen (KDS) oder in den QoE-Datenbanken (Quality of Experience) protokolliert werden. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per E-Mail, Sofortnachricht oder SMS benachrichtigt werden. (SMS oder Kurznachrichtendienst ist die Technologie, die zum Senden von Textnachrichten von einem mobilen Gerät an ein anderes verwendet wird.)

    > [!NOTE]
    >  Ausführliche Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter [Konfigurieren von Benachrichtigungen.](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))

- **Das Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) testet wichtige Skype for Business Server Komponenten proaktiv, z. B. die Anmeldung beim System, den Austausch von Chatnachrichten oder das Tätigen von Anrufen an ein Telefon im Telefonfestnetz (Public Switched Telephone Network, PSTN). Diese Tests werden mithilfe der cmdlets für synthetische Transaktionen Skype for Business Server durchgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn diese simulierte Unterhaltung fehlschlägt, wird eine Warnung generiert.

Das Importieren der Management Packs ist ein wichtiger Schritt. Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht verwenden, um Skype for Business Server Ereignisse zu überwachen oder Skype for Business Server synthetische Transaktionen auszuführen.

Das Component and User Management Pack wird verwendet, um nur Skype for Business Server 2019 zu überwachen. Wenn Sie sich in einem Koexistenzszenario befinden, in dem sowohl Skype for Business Server 2019 als auch Skype for Business Server 2015 installiert sind, sollten Sie weiterhin die Skype for Business Server 2015 Management Packs für Ihre Skype for Business Server 2015-Computer verwenden.

> [!NOTE]
> Management Packs für Skype for Business Server 2019 enthalten das Skype for Business Server 2019 Component and User Management Pack und das Skype for Business Server 2019 Active Monitoring Management Pack.

Zum Importieren der Management Packs können folgende Tools verwendet werden:

- **System Center Operations Manager** Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für Skype for Business Server hinzuzufügen.

- **Operations Manager-Shell** Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs auftreten, indem Sie die System Center Operations Manager-Konsole verwenden.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mithilfe von System Center Operations Manager

1. Laden Sie die SkypeForBusiness2019ManagementPacks.msi aus dem Microsoft Web herunter, und installieren Sie die MSI-Datei.

2. Klicken Sie in System Center Operations Manager auf **"Administration".**

3. Klicken Sie auf der Verwaltungsseite mit der rechten Maustaste auf Management Packs, und klicken Sie anschließend auf **Management Packs importieren**.

4. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5. Klicken Sie im Dialogfeld **"Onlinekatalogverbindung"** auf **"Nein".**

6. Suchen Sie im Dialogfeld **"Zu importierende Management Packs auswählen"** die Dateien Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp und Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, und klicken Sie dann auf **"Öffnen".** Um mehrere Dateien im Dialogfeld auszuwählen, klicken Sie auf die erste Datei, halten Sie dann die STRG-TASTE gedrückt und klicken Sie auf die nachfolgenden Dateien.

7. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Kopieren Sie in diesem Fall die Dateien in einen anderen Ordner, und starten Sie dann den Import- und Installationsvorgang neu.

8. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Der Import- und Installationsvorgang kann mehrere Minuten dauern.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importieren der Management Packs mithilfe der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mithilfe der Operations Manager-Konsole zu importieren. Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, stellt die Konsole nicht immer ausreichende Fehlerberichte bereit. Im Vergleich dazu liefert die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Paket mithilfe der Operations Manager-Shell. Anhand der von Operations Manager-Shell bereitgestellten Informationen können Sie ermitteln, warum der Import fehlgeschlagen ist.

1. Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **"Microsoft System Center 2012",** auf **"Betriebs-Manager"** und dann auf **Operations Manager-Shell**.

2. Geben Sie in Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp ein, und drücken Sie dann die EINGABETASTE:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang unter Verwendung des Pfads zu Ihrer Kopie der Datei Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```