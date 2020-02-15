---
title: Konfigurieren des primären Verwaltungsservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Zusammenfassung: Konfigurieren des primären Verwaltungsservers, Installieren von System Center Operations Manager und Importieren von Management Packs für Skype for Business Server 2015.'
ms.openlocfilehash: 08c1967965248d26844433030e4bf77501882cd8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005960"
---
# <a name="configure-the-primary-management-server"></a>Konfigurieren des primären Verwaltungsservers

**Zusammenfassung:** Konfigurieren des primären Verwaltungsservers, Installieren von System Center Operations Manager und Importieren von Management Packs für Skype for Business Server 2015.

Um die neuen Integritäts Überwachungsfunktionen in Skype for Business Server 2015 optimal nutzen zu können, müssen Sie zunächst einen Computer festlegen, der als primärer Verwaltungs Server fungieren soll. Anschließend müssen Sie System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 auf diesem Computer installieren. Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server installieren, die als Operations Manager-Back-End-Datenbank fungiert.

Bei der Installation von System Center Operations Manager müssen Sie alle Komponenten des Produkts installieren, einschließlich:

- Betriebsdatenbank

- Server

- Konsole

- Windows PowerShell-Cmdlets

- Webkonsole

- Reporting

- Data Warehouse

> [!IMPORTANT]
> Das "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" muss installiert werden, bevor Sie System Center Operations Manager 2012 installieren.

Ausführliche Informationen zu diesen Produkten und deren Installation finden Sie unter den folgenden Links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center-Operations Manager 2007](https://technet.microsoft.com/library/bb735860.aspx)

Beachten Sie, dass pro Skype for Business Server-Bereitstellung nur ein Stamm Verwaltungs Server vorhanden sein kann.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importieren der Skype for Business Server 2015 Management Packs

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die bestimmt, welche Elemente System Center Operations Manager überwachen kann, wie diese Elemente überwacht werden sollen und wie Warnungen ausgelöst werden sollen und gemeldet. Skype for Business Server 2015 enthält zwei System Center Operations Manager-Management Packs, die die folgenden Funktionen bieten:

- **Das Component and User Management Pack** (Microsoft.ls.2015.Monitoring.ComponentAndUser.MP) verfolgt Skype for Business Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den CDRs (Call Detail Records) oder in den QoE-Datenbanken (Quality of Experience) protokolliert wurden. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort über e-Mail, Sofortnachrichten oder SMS benachrichtigt werden. (SMS oder kurzer Nachrichtendienst ist die Technologie, mit der Textnachrichten von einem Mobilgerät an ein anderes gesendet werden.)

    > [!NOTE]
    >  Ausführliche Informationen zum Konfigurieren von Operations Manager-Benachrichtigungen finden Sie unter [Konfigurieren von Benachrichtigungen](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Das Active Monitoring Management Pack** (Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP) testet die Schlüssel Skype for Business Server Komponenten proaktiv, beispielsweise das Anmelden beim System, das Austauschen von Chatnachrichten oder das tätigen von Anrufen an ein Telefon im öffentlichen Telefonnetz (PSTN). Diese Tests werden mithilfe der Cmdlets für synthetische Transaktionen Skype for Business Server ausgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn diese simulierte Unterhaltung fehlschlägt, wird eine Warnung generiert.

Das Importieren der Management Packs ist ein wichtiger Schritt. Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht verwenden, um Skype for Business Server Ereignisse zu überwachen oder Skype for Business Server synthetische Transaktionen auszuführen.

Das Komponenten-und das User Management Pack werden nur Skype for Business Server 2015 überwacht. Wenn Sie sich in einem Szenario mit Koexistenz befinden, in dem sowohl Skype for Business Server 2015 als auch lync Server 2013 installiert sind, sollten Sie weiterhin die lync Server 2013 Management Packs für Ihre lync Server 2013 Computer verwenden.

> [!NOTE]
> Zu den Management Packs für Skype for Business Server 2015 gehören die Skype for Business Server 2015-Komponente und das User Management Pack sowie das Skype for Business Server 2015 Active Monitoring Management Pack.

Zum Importieren der Management Packs können folgende Tools verwendet werden:

- **System Center Operations Manager** Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für Skype for Business Server hinzuzufügen.

- **Operations Manager-Shell** Sie können die Operations Manager-Shell verwenden, um direkt zu importieren, oder um Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mithilfe von System Center Operations Manager

1. Laden Sie die SkypeForBusiness2015ManagementPacks. msi aus den Microsoft-Webdownloads herunter, und installieren Sie die MSI-Datei.

2. Klicken Sie in System Center Operations Manager auf **Verwaltung**.

3. Klicken Sie auf der **** Verwaltungsseite mit der rechten Maustaste auf Management Packs, und klicken Sie anschließend auf **Management Packs importieren**.

4. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5. Klicken Sie im Dialogfeld **Online Katalogverbindung** auf **Nein**.

6. Suchen Sie im Dialogfeld **zu importierende Management Packs auswählen nach** den Dateien Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP und Microsoft.ls.2015.Monitoring.ComponentAndUser.MP, und klicken Sie dann auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie die STRG-Taste gedrückt, und klicken Sie dann auf die nachfolgenden Dateien.

7. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. In diesem Fall kopieren Sie die Dateien in einen anderen Ordner, und starten Sie dann den Import-und Installationsvorgang neu.

8. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Der Import-und Installationsvorgang kann mehrere Minuten in Anspruch setzen.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importieren der Management Packs mithilfe der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mithilfe der Operations Manager-Konsole zu importieren. Wenn jedoch ein Fehler auftritt und der Import fehlschlägt, stellt die Konsole nicht immer angemessene Fehlerberichte bereit. Im Vergleich dazu enthält die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Probleme auftreten, importieren Sie das Paket mithilfe der Operations Manager-Shell. Mithilfe der von Operations Manager-Shell bereitgestellten Informationen können Sie ermitteln, warum der Import fehlgeschlagen ist.

1. Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft System Center 2012**, dann auf **Operations Manager**, und klicken Sie dann auf **Operations Manager-Shell**.

2. Geben Sie in Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein, wobei Sie den tatsächlichen Pfad zu Ihrer Kopie der Datei Microsoft.ls.2015.Monitoring.ActiveMonitoring.MP verwenden, und drücken Sie dann die EINGABETASTE:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang, indem Sie den Pfad zu Ihrer Kopie der Datei Microsoft.ls.2015.Monitoring.ComponentAndUser.MP:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
