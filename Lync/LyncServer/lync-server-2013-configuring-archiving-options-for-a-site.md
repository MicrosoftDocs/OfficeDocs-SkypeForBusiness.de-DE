---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen für eine Website'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Konfigurieren von Archivierungsoptionen für eine Website in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Sie können Archivierungsoptionen angeben, die auf bestimmte Websites angewendet werden sollen, indem Sie Optionen in einer Archivierungskonfiguration für jede dieser Websites erstellen und konfigurieren. Eine Standortkonfiguration überschreibt die globale Konfiguration, aber nur für den in der Standortkonfiguration angegebenen Standort. Pool Konfigurationen überschreiben Websitekonfigurationen

Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für Global-, Website-und Poolkonfigurationen, finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation .

<div>


> [!NOTE]  
> Sie sollten alle geeigneten Optionen in den Archivierungs Konfigurationen angeben, bevor Sie die Archivierung aktivieren.



</div>

<div>


> [!IMPORTANT]  
> Um die Archivierung zu aktivieren, müssen Sie Archivierungsrichtlinien angeben, um die Archivierung interner und externer Kommunikation auf globaler Ebene und gegebenenfalls auf Website-und Benutzerebene zu steuern. Wenn Sie Richtlinien auf Benutzerebene konfigurieren, müssen Sie die Benutzerrichtlinien auch bestimmten Benutzern zuweisen. Ausführliche Informationen zum Erstellen und Konfigurieren von Archivierungsrichtlinien finden Sie unter <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>So konfigurieren Sie Archivierungsoptionen auf Websiteebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server 2013-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.

5.  Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.

6.  Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
      - Um sowohl Chatsitzungen als auch Konferenzen zu archivieren, klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**.
    
      - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.

7.  Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
      - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

8.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

