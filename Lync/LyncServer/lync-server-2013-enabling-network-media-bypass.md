---
title: Aktivieren der Netzwerkmedienumgehung
TOCTitle: Aktivieren der Netzwerkmedienumgehung
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182552(v=OCS.15)
ms:contentKeyID: 49294808
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Netzwerkmedienumgehung

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Die Einstellungen für die Medienumgehung gelten global für eine Microsoft Lync Server 2013-Bereitstellung. Die Medienumgehung ermöglicht bei Anrufen die Umgehung des Vermittlungsservers. Weitere Informationen zur Verwendung der Medienumgehung finden Sie unter [Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) im Abschnitt zur Planung.

Sie können die Medienumgehung über die Lync Server-Systemsteuerung aktivieren und konfigurieren.

## So aktivieren und konfigurieren Sie die Medienumgehung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.

4.  Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**. Es ist immer nur eine Konfiguration vorhanden, und diese trägt stets den Namen "Global".

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** auf das Kontrollkästchen **Medienumgehung aktivieren**.

7.  Wählen Sie eine der folgenden Optionen aus:
    
      - **Immer umgehen**   Wählen Sie diese Option aus, um eine Medienumgehung für alle Anrufe anzustreben. Diese Option ist nicht verfügbar, wenn die Anrufsteuerung aktiviert ist. Ist die Anrufsteuerung nicht aktiviert, wählen Sie diese Option in den folgenden Situationen:
        
          - Es besteht keine Notwendigkeit zur Bandbreitensteuerung.
        
          - Es ist keine fein abgestimmte Konfiguration erforderlich, mit der die Anforderung einer Medienumgehung erkannt wird.
        
          - Zwischen Gateways und Clients ist vollständige Konnektivität gegeben.
    
      - **Konfiguration von Standorten und Regionen verwenden**   Wenn die Anrufsteuerung aktiviert wurde, ist diese Option standardmäßig aktiviert und kann nicht geändert werden. Ist diese Option ausgewählt, wird anhand der Standorte und Regionen in der Netzwerkkonfiguration ermittelt, ob eine Medienumgehung möglich ist. Wenn Sie diese Option auswählen, können Sie eine Umgehung für Standorte aktivieren, die nicht zugeordnet sind. Aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren** nur dann, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die mit einer bestimmten Region verknüpft sind, und Sie außerdem über einige Zweigstellen mit Bandbreiteneinschränkungen verfügen, die mit derselben Region verknüpft sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die mit den Zweigstandorten verknüpften Subnetze angeben, statt sämtliche, mit allen Standorten verknüpfte Subnetze angeben zu müssen. Es wird empfohlen, das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte** nicht zu aktivieren, wenn die Anrufsteuerung aktiviert ist.

8.  Klicken Sie auf **Commit**, um Ihre Änderungen zu speichern.

## Siehe auch

#### Aufgaben

[Deaktivieren der Netzwerkmedienumgehung](lync-server-2013-disabling-network-media-bypass.md)  

#### Konzepte

[Optionen für die globale Medienumgehung in Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Weitere Ressourcen

[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)

