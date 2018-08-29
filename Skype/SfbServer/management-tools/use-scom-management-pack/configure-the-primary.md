---
title: Konfigurieren des primären Verwaltungsservers
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 'Zusammenfassung: Konfigurieren Sie Ihren primären Verwaltungsserver, Installieren von System Center Operations Manager und Importieren des Management Packs für Skype für Business Server 2015.'
ms.openlocfilehash: d976c0daa6c53896b0a87dd9478174496aba8af6
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250808"
---
# <a name="configure-the-primary-management-server"></a>Konfigurieren des primären Verwaltungsservers

**Zusammenfassung:** Konfigurieren Sie Ihren primären Verwaltungsserver, Installieren von System Center Operations Manager und Importieren des Management Packs für Skype für Business Server 2015.

Um die neue Integritätsüberwachung in Skype für Business Server 2015 enthaltene Funktionen nutzen, müssen Sie zuerst einen Computer als Ihren primären Verwaltungsserver festlegen. Sie müssen die System Center Operations Manager 2012 SP1 oder R2 oder System Center Operations Manager 2007 R2 klicken Sie dann auf diesem Computer installieren. Darüber hinaus müssen Sie zuerst eine unterstützte Version von SQL Server dienen als Back-End-Datenbank Operations Manager installieren.

Bei der Installation von System Center Operations Manager müssen Sie zum Installieren aller Komponenten des Produkts, einschließlich:

- Betriebsdatenbank

- Server

- Konsole

- Windows PowerShell-cmdlets

- Webkonsole

- Berichterstellung

- Data Warehouse

> [!IMPORTANT]
> "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" muss vor dem Installieren von System Center Operations Manager 2012 installiert werden.

Ausführliche Informationen zu diesen Produkten und ihrer Installation finden Sie unter folgenden Links:

- [System Center Operations Manager 2012](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [System Center Operations Manager 2007](https://technet.microsoft.com/en-us/library/bb735860.aspx)

Behalten Sie im Hinterkopf können Sie nur eine Stammverwaltungsserver pro Skype für Business Server-Bereitstellung haben.

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a>Importieren der Skype for Business Server 2015 Management Packs

Sie können die Funktionen von System Center Operations Manager durch Installieren von Management Packs erweitern – Software, die bestimmt, welche Elemente von System Center Operations Manager überwachen können, wie diese Elemente überwacht werden soll und wie Warnungen ausgelöst werden soll, und gemeldet. Skype für Business Server 2015 umfasst zwei System Center Operations Manager Management Packs, die die folgenden Funktionen bereitstellen:

- **Die Komponente und User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) verfolgt Skype für Business Server Probleme in den Ereignisprotokollen aufgezeichnet, durch die Leistungsindikatoren registriert oder in der kommunikationsdatensätze (KDS) oder die Datenbanken Quality of Experience (QoE) angemeldet. Für kritische Probleme können System Center Operations Manager konfiguriert werden, um Administratoren über e-Mail, Sofortnachricht oder SMS messaging sofort zu benachrichtigen. (SMS ist die Technologie, die verwendet wird, um Textnachrichten von einem Mobilgerät an ein anderes zu senden.)

    > [!NOTE]
    >  Ausführliche Informationen zum Konfigurieren von Operations Manager-Benachrichtigung finden Sie unter [Konfigurieren der Benachrichtigung](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).

- **Das aktive Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) Schlüssel proaktiv Tests Skype für Business Server-Komponenten, beispielsweise auf das System anmeldet, Sofortnachrichten austauschen oder tätigen von Anrufen bei einem Telefon befindet sich auf dem öffentlichen Telefonfestnetz (PSTN ). Diese Tests werden mithilfe der Skype for Business Server-Cmdlets für synthetische Transaktionen durchgeführt. Zum Beispiel wird das **Test-CsIM**-Cmdlet verwendet, um eine Sofortnachrichtenunterhaltung zwischen zwei Testbenutzern zu simulieren. Wenn bei dieser simulierten Nachrichtenunterhaltung ein Fehler auftritt, wird eine Benachrichtigung erzeugt.

Das Importieren der Management Packs ist ein wichtiger Schritt. Wenn die Management Packs nicht importiert werden, können Sie Operations Manager nicht zum Überwachen von Skype for Business Server-Ereignissen verwenden und keine synthetischen Skype for Business Server-Transaktionen ausführen.

Das Component and User Management Pack wird nur zum Überwachen von Skype for Business Server 2015 verwendet. Wenn Sie sich in einem Koexistenzszenario befinden, wo sowohl Skype for Business Server 2015 als auch Lync Server 2013 installiert sind, sollten Sie weiterhin die Lync Server 2013 Management Packs für Ihre Lync Server 2013-Computer verwenden.

> [!NOTE]
> Management Packs für Skype for Business Server 2015 umfassen das Skype for Business Server 2015 Component and User Management Pack und das Skype for Business Server 2015 Active Monitoring Management Pack.

Zum Importieren der Management Packs können folgende Tools verwendet werden:

- **System Center Operations Manager** Mit dieser Methode verwenden Sie die Operations Manager überwachen für Skype für Business Server hinzufügen.

- **Operations Manager-Shell** Sie können der Operations Manager-Shell verwenden, um direkt importieren oder um alle Probleme zu behandeln, die beim Importieren der Management Packs mithilfe von System Center Operations Manager-Konsole auftreten.

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a>Importieren der Management Packs mit System Center Operations Manager

1. Laden Sie die Datei SkypeForBusiness2015ManagementPacks.msi über die Microsoft Web-Downloads herunter und installieren Sie die Datei.

2. Klicken Sie in System Center Operations Manager auf **Verwaltung**.

3. Klicken Sie im Bereich Verwaltung Maustaste auf **Management Packs**, und klicken Sie dann auf **Management Packs importieren**.

4. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Hinzufügen** und anschließend auf **Von Datenträger hinzufügen**.

5. Im Dialogfeld **Verbindung mit dem Onlinekatalog** klicken Sie auf **Keine**.

6. Suchen Sie im Dialogfeld **Zu importierende Management Packs auswählen** die Dateien Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp und Microsoft.LS.2015.Monitoring.ComponentAndUser.mp und wählen Sie sie aus und klicken Sie anschließend auf **Öffnen**. Wenn Sie mehrere Dateien im Dialogfeld auswählen möchten, klicken Sie auf die erste Datei, halten Sie dann die STRG-Taste gedrückt und klicken Sie dann auf alle weiteren Dateien.

7. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Installieren**. Wenn eine Fehlermeldung angezeigt wird und bei der Installation ein Fehler auftritt, bedeutet das normalerweise, dass sich die Management Pack-Dateien in einem Ordner befinden, der durch die Windows-Benutzerkontensteuerung geschützt ist. Wenn dies der Fall ist, kopieren Sie die Dateien in einen anderen Ordner und starten Sie den Import- und Installationsvorgang erneut.

8. Klicken Sie im Dialogfeld **Management Packs auswählen** auf **Schließen**. Der Import- und Installationsvorgang kann mehrere Minuten dauern.

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a>Importieren der Management Packs mit der Operations Manager-Shell

Im Allgemeinen ist es einfacher, die Management Packs mit der Operations Manager-Konsole zu importieren. Wenn jedoch ein Fehler auftritt und bei der Installation Fehler auftreten, stellt die Konsole nicht immer ausreichende Fehlerberichte bereit. Im Vergleich dazu bietet die Operations Manager-Shell detaillierte Informationen. Wenn Sie Operations Manager verwenden und beim Importieren eines Management Packs Fehler auftreten, importieren Sie das Management Pack mit der Operations Manager-Shell. Die Operations Manager-Shell kann weitere hilfreiche Informationen bieten, um festzustellen, warum beim Import Fehler aufgetreten sind.

1. Klicken Sie auf **Start**, klicken Sie dann auf **Alle Programme**, anschließend auf **Microsoft System Center 2012**, dann auf **Operations Manager** und anschließend auf **Operations Manager-Shell**.

2. Geben Sie in der Operations Manager-Shell den folgenden Befehl an der Eingabeaufforderung ein und drücken Sie die EINGABETASTE. Verwenden Sie dabei den tatsächlichen Pfad zur Kopie der Datei „Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp“:

  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
  ```

3. Wiederholen Sie nach dem Importieren des ersten Management Packs den Prozess, indem Sie den Pfad zur Kopie der Datei „Microsoft.LS.2015.Monitoring.ComponentAndUser.mp“ verwenden:

  ```
  Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
  ```