---
title: Konfigurieren von Archivierungsoptionen für einen Pool
TOCTitle: Konfigurieren von Archivierungsoptionen für einen Pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205200(v=OCS.15)
ms:contentKeyID: 49295185
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Archivierungsoptionen für einen Pool

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Sie können Archivierungsoptionen angeben, die auf spezifische Pools angewendet werden, indem Sie für jeden dieser Pools bei einer Archivierungskonfiguration Optionen erstellen und konfigurieren. Eine Pool-Konfiguration überschreibt die globale Konfiguration und die Standortkonfiguration, jedoch nur für den in der Pool-Konfiguration angegebenen Pool.

Ausführliche Informationen über die Funktionsweise von Archivierungskonfigurationen, einschließlich der Hierarchie für globale, Standort- und Pool-Konfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Sie sollten alle entsprechenden Optionen in den Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren. Einzelheiten finden Sie unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A> in der Bereitstellungsdokumentation.



## So konfigurieren Sie Archivierungsoptionen auf Pool-Ebene

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster und geben Sie dann die Admin-URL ein, um Systemsteuerung für Lync Server 2013 zu öffnen. Ausführliche Informationen über die verschiedenen Methoden, die Sie zum Start von Systemsteuerung für Lync Server 2013 verwenden können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Pool-Konfiguration**.

5.  Wählen Sie in **Dienst auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.

6.  Wählen Sie unter **Neue Archivierungseinstellung** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungseinstellungen aus:
    
      - **Archivierung deaktivieren**
    
      - **IM-Sitzungen archivieren**
    
      - **IM- und Webkonferenzsitzungen archivieren**

7.  Führen Sie außerdem auf der Seite **Neue Archivierungseinstellung** die folgenden Schritte aus:
    
      - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden, markieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**.
    
      - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

8.  Klicken Sie auf **Commit**.

