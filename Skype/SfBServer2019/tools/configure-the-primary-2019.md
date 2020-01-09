---
title: Konfigurieren des primären Verwaltungsservers
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2019.'
ms.openlocfilehash: b5835f0638231cff6176aa7377d6f7c60e81b6f7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989070"
---
# <a name="configure-the-primary-management-server"></a>Konfigurieren des primären Verwaltungsservers

**Zusammenfassung:** Konfigurieren Sie Ihren primären Verwaltungsserver, installieren Sie System Center Operations Manager, und importieren Sie Management Packs für Skype for Business Server 2019.

Um die neuen Integritäts Überwachungsfunktionen in Skype for Business Server 2019 optimal nutzen zu können, müssen Sie zunächst einen Computer als primären Verwaltungs Server festlegen. Sie müssen dann System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 auf diesem Computer installieren. Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server installieren, um als Operations Manager-Back-End-Datenbank zu funktionieren.

Wenn Sie System Center Operations Manager installieren, müssen Sie alle Komponenten dieses Produkts installieren, einschließlich:

- Betriebsdatenbank

- Server

- Konsole

- Windows PowerShell-Cmdlets

- Webkonsole

- Berichterstellung

- Data Warehouse

> [!IMPORTANT]
> Bevor Sie System Center Operations Manager 2012 installieren, muss das "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" installiert werden.

Ausführliche Informationen zu diesen Produkten und ihrer Installation finden Sie unter folgenden Links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Beachten Sie, dass pro Skype for Business Server-Bereitstellung nur ein Stammverwaltungsserver vorhanden sein kann.

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a>Importieren der Skype for Business Server 2019-Management Packs

Sie können die Funktionen von System Center Operations Manager erweitern, indem Sie Management Packs installieren – Software, die festlegt, welche Elemente System Center Operations Manager überwachen kann, wie diese Elemente überwacht werden sollen und wie Benachrichtigungen ausgelöst werden sollen und berichtet. Skype for Business Server 2019 umfasst zwei System Center Operations Manager-Verwaltungspakete, die die folgenden Funktionen bieten:

- **Das Komponenten-und Benutzer Verwaltungspaket** (Microsoft.ls.2019.Monitoring.ComponentAndUser.MP) verfolgt Skype for Business-Server Probleme, die in Ereignisprotokollen aufgezeichnet, von Leistungsindikatoren registriert oder in den Anruf Detaildatensätzen (CDRs) oder den QoE-Datenbanken (Quality of Experience) protokolliert wurden. Bei kritischen Problemen kann System Center Operations Manager so konfiguriert werden, dass Administratoren sofort per e-Mail, Sofortnachricht oder SMS benachrichtigt werden. (SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.)

    > [!NOTE]
    >  Details zum Konfigurieren der Operations Manager-Benachrichtigung finden Sie unter [Konfigurieren der Benachrichtigung](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Das Active Monitoring Management Pack** (Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP) testet die wichtigen Komponenten von Skype for Business Server proaktiv, wie beispielsweise die Anmeldung beim System, den Austausch von Sofortnachrichten oder das Anrufen an ein Telefon, das sich im öffentlichen Telefonnetz (PSTN) befindet. Diese Tests werden mithilfe der Skype for Business Server-Cmdlets für synthetische Transaktionen durchgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.

Das Importieren der Management Packs ist ein wichtiger Schritt. Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht zum Überwachen von Skype for Business Server-Ereignissen verwenden und keine synthetischen Skype for Business Server-Transaktionen ausführen.

Das Komponenten-und Benutzer Verwaltungspaket wird zum Überwachen von Skype for Business Server 2019 verwendet. Wenn Sie sich in einem Koexistenz-Szenario befinden, in dem Skype for Business Server 2019 und Skype for Business Server 2015 installiert sind, sollten Sie weiterhin die Skype for Business Server 2015-Management Packs für Ihre Skype for Business Server 2015-Computer verwenden.

> [!NOTE]
> Zu den Management Packs für Skype for Business Server 2019 gehören die Skype for Business Server 2019-Komponente und das User Management Pack sowie das Active Monitoring-Management Pack für Skype for Business Server 2019.

Zum Importieren der Management Packs können folgende Tools verwendet werden:

- **System Center Operations Manager** Mit dieser Methode verwenden Sie den Operations Manager, um die Überwachung für Skype for Business Server hinzuzufügen.

- **Operations Manager-Shell** Sie können die Operations Manager-Shell verwenden, um direkt zu importieren oder Probleme zu beheben, die beim Importieren von Management Packs mithilfe der System Center Operations Manager-Konsole auftreten.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mit System Center Operations Manager

1. Laden Sie die Datei "SkypeForBusiness2019ManagementPacks. msi" aus den Microsoft Web Downloads herunter, und installieren Sie die MSI-Datei.

2. Klicken Sie in System Center Operations Manager auf **Verwaltung**.

3. Klicken Sie im Verwaltungsbereich mit der rechten Maustaste auf **Management Packs**, und klicken Sie dann auf **Management Packs importieren**.

4. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5. Im Dialogfeld **Verbindung mit dem Onlinekatalog** klicken Sie auf **Keine**.

6. Suchen Sie im Dialogfeld **zu importierende Management Packs auswählen nach** den Dateien Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP und Microsoft.ls.2019.Monitoring.ComponentAndUser.MP, und klicken Sie dann auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie dann die STRG-Taste gedrückt und klicken Sie dann auf alle weiteren Dateien.

7. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner und starten Sie den Import- und Installationsvorgang erneut.

8. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Der Import- und Installationsvorgang kann mehrere Minuten dauern.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importieren der Management Packs mit der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mit der Operations Manager-Konsole zu importieren. Wenn jedoch ein Fehler auftritt und bei der Installation Fehler auftreten, stellt die Konsole nicht immer ausreichende Fehlerberichte bereit. Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Fehler auftreten, importieren Sie das Management Pack mit der Operations Manager-Shell. Die Operations Manager-Shell kann weitere hilfreiche Informationen bieten, um festzustellen, warum beim Import Fehler aufgetreten sind.

1. Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.

2. Geben Sie in der Operations Manager-Shell an der Eingabeaufforderung den folgenden Befehl unter Verwendung des tatsächlichen Pfads zu Ihrer Kopie der Datei Microsoft.ls.2019.Monitoring.ActiveMonitoring.MP ein, und drücken Sie dann die EINGABETASTE:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. Nachdem Sie das erste Management Pack importiert haben, wiederholen Sie den Vorgang, indem Sie den Pfad zu Ihrer Kopie der Datei Microsoft.ls.2019.Monitoring.ComponentAndUser.MP:

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
