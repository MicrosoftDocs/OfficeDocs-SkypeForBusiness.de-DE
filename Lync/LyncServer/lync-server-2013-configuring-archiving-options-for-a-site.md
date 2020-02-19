---
title: 'Lync Server 2013: Konfigurieren von Archivierungsoptionen für einen Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9b679eabfc0538de5daf59ee1eb7742ade94228
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Konfigurieren von Archivierungsoptionen für eine Website in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Sie können Archivierungsoptionen für bestimmte Standorte angeben, indem Sie entsprechende Optionen in einer Archivierungskonfiguration für die betreffenden Standorte erstellen und konfigurieren. Eine Standortkonfiguration überschreibt die globale Konfiguration. Dies gilt jedoch nur für den in der Standortkonfiguration angegebenen Standort. Standortkonfigurationen werden von Poolkonfigurationen überschrieben.

Ausführliche Informationen zur Funktionsweise von Archivierungs Konfigurationen, einschließlich der Hierarchie für globale, Standort-und Poolkonfigurationen, finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren.



</div>

<div>


> [!IMPORTANT]  
> Zum Aktivieren der Archivierung müssen Sie Archivierungsrichtlinien angeben, um die Archivierung der internen und externen Kommunikation auf globaler Ebene und gegebenenfalls auf Standort-und Benutzerebene zu steuern. Wenn Sie Richtlinien auf Benutzerebene konfigurieren, müssen Sie auch die Benutzerrichtlinien bestimmten Benutzern zuweisen. Ausführliche Informationen zum Erstellen und Konfigurieren von Archivierungsrichtlinien finden Sie unter <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>So konfigurieren Sie die Archivierungsoptionen auf Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die CsArchivingAdministrator- oder die CsAdministrator-Rolle zugewiesen wurde, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die lync Server 2013-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server 2013 Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.

5.  Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.

6.  Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
      - Um nur Sofortnachrichtensitzungen zu archivieren, klicken Sie auf **Sofortnachrichtensitzungen archivieren**.
    
      - Klicken Sie auf **IM- und Webkonferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
      - Um die Archivierung für die Richtlinie zu deaktivieren, klicken Sie auf **Archivierung deaktivieren**.

7.  Gehen Sie unter **Neue Archivierungseinstellung** wie folgt vor:
    
      - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um die Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Um Exchange Server zum Speichern von Archivierungsdaten zu verwenden, klicken Sie auf das Kontrollkästchen **Integration der Microsoft Exchange** .
    
      - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

8.  Klicken Sie auf **Commit ausführen**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

