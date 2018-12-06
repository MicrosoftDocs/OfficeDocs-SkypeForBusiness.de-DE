---
title: Bereitstellen von Lync Server 2013-Clients
TOCTitle: Bereitstellen von Lync Server 2013-Clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204883(v=OCS.15)
ms:contentKeyID: 49293984
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von Lync Server 2013-Clients

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Nach dem Migrieren von Benutzern zu Lync Server 2013 führen Sie die folgenden Schritte aus:

1.  Verwenden Sie den Clientversionsfilter auf dem neuen Lync Server 2013-Server, um nur Clients, auf denen die neuesten Updates installiert sind, die Anmeldung zu erlauben.

2.  Konfigurieren Sie, falls erforderlich, die Gruppenrichtlinieneinstellungen, die für das Clientbootstrapping benötigt werden. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter [Konfigurieren von Richtlinien für das Clientbootstrapping in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md). Diese Einstellungen müssen nur dann konfiguriert werden, wenn Sie vorhandene Clientbootstrapping-Richtlinien ändern oder neue Clientbootstrapping-Richtlinien festlegen möchten. Wenn Sie keine Clientbootstrapping-Richtlinien konfigurieren möchten oder Clientbootstrapping-Richtlinien der Vorgängerversion gültig bleiben sollen, ist keine Aktion erforderlich.

3.  Konfigurieren Sie andere Benutzer- und Clientrichtlinien für einzelne Benutzer oder Benutzergruppen mit der Systemsteuerung für Lync Server 2013, der Verwaltungsshell für Lync Server 2013 oder mit beiden. Nähere Informationen finden Sie in der Planungsdokumentation unter [Neue und geänderte Einstellungen für Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md).

4.  Stellen Sie die neueste Version von Lync Server 2013 zusammen mit den neuesten kumulativen Updates bereit. Nähere Informationen finden Sie in der Bereitstellungsdokumentation unter [Bereitstellen von Clients und Geräten in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md).

5.  (Optional) Wenn für Ihre Organisation der Datenschutzmodus für erweiterte Anwesenheitsinformationen von Lync Server 2013 erforderlich ist, definieren Sie nach Abschluss der Migration eine Regel für die Clientversionsrichtlinie, mit der verhindert wird, dass frühere Clientversionen sich anmelden können. Aktivieren Sie anschließend den Datenschutzmodus für erweiterte Anwesenheitsinformationen.
    

    > [!IMPORTANT]
    > Aktivieren Sie den Datenschutzmodus für erweiterte Anwesenheitsinformationen von Lync 2013 erst dann, wenn jeder Benutzer in einem gegebenen Serverpool die neuesten Clientversionen installiert hat.


