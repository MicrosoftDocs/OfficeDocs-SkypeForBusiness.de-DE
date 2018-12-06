---
title: Konfigurieren der globalen Richtlinie für die Archivierung
TOCTitle: Konfigurieren der globalen Richtlinie für die Archivierung
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204906(v=OCS.15)
ms:contentKeyID: 49294072
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der globalen Richtlinie für die Archivierung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Wenn Sie Ihre Front-End-Server bereitstellen, erstellt Lync Server eine globale Richtlinie für die Archivierung. Die Archivierung ist in der globalen Richtlinie standardmäßig deaktiviert. Die globale Richtlinie legt fest, ob die Archivierung der internen und der externen Kommunikation für die gesamte Bereitstellung aktiviert oder deaktiviert wird. Sie kann durch Standort- oder Benutzerrichtlinien überschrieben werden. Dies gilt auch, wenn Sie die Microsoft Exchange-Integration für einige oder alle Benutzer verwenden. Wenn Sie die Microsoft Exchange-Integration verwenden, gilt die globale Richtlinie nicht für Benutzer, die in Exchange 2013 verwaltet werden und deren Postfächer sich im Compliance-Archiv befinden.

Nähere Informationen über die Funktionsweise der Archivierungsrichtlinien, einschließlich der Hierarchie der Richtlinien auf globaler Ebene sowie auf Standort- und Benutzerebene, finden Sie in der Planungs-, Bereitstellungs- oder Betriebsdokumentation unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md).


> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, bestimmen die Richtlinien für das Compliance-Archiv von Exchange, ob die Archivierung für Benutzer aktiviert wird, die in Exchange 2013 verwaltet werden und deren Postfächer sich im Compliance-Archiv befinden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung beim Verwenden von Exchange Server-Integration</A>.<BR>Konfigurieren Sie alle erforderlichen Optionen in den Archivierungseinstellungen, bevor Sie die Archivierung aktivieren. Ausführliche Informationen hierzu finden Sie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-configuring-archiving-options.md">Konfigurieren von Archivierungsoptionen</A>.



## So konfigurieren Sie die globale Richtlinie für die Archivierung zur Verwendung der Lync Server-Archivierungsdatenbanken

1.  Melden Sie sich mit einem Benutzerkonto, dem die CsArchivingAdministrator- oder die CsAdministrator-Rolle zugewiesen wurde, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um das Systemsteuerung für Lync Server 2013 zu öffnen. Nähere Informationen zu den einzelnen Methoden, mit denen Sie Systemsteuerung für Lync Server 2013 starten können, finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungsrichtlinie**.

4.  Klicken Sie auf der Seite **Archivierungsrichtlinie** auf **Global**, auf **Edit** und dann auf **Details anzeigen**.

5.  Führen Sie im Abschnitt **Bearbeiten der Archivierungsrichtlinie – Global** folgende Aktionen aus:
    
      - Geben Sie im Feld **Name** einen neuen Namen für die globale Richtlinie ein, wenn Sie den Standardnamen "Global" nicht verwenden möchten.
    
      - Geben Sie im Feld **Beschreibung** Informationen zur Gestalt der Richtlinie ein (z. B. globale Richtlinie für *Abteilungsname*).
    
      - Um die Archivierung der internen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Interne Kommunikation archivieren**.
    
      - Um die Archivierung der externen Kommunikation für alle Standorte und Benutzer zu kontrollieren, die nicht explizit durch eine Standort- oder Benutzerrichtlinie gesteuert wird, aktivieren oder deaktivieren Sie das Kontrollkästchen **Externe Kommunikation archivieren**.

6.  Klicken Sie auf **Commit**.

