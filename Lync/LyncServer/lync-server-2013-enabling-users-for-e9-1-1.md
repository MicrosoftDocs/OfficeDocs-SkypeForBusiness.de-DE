---
title: 'Lync Server 2013: Aktivieren von Benutzern für E9-1-1'
TOCTitle: Aktivieren von Benutzern für E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425892(v=OCS.15)
ms:contentKeyID: 49293745
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von Benutzern für E9-1-1 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

Lync Server verwendet während der Clientregistrierung eine Ortungsrichtlinie, um die E9-1-1-Eigenschaften für Benutzer zu aktivieren, bei denen Enterprise-VoIP aktiviert ist. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Die Ortungsrichtlinie enthält beispielsweise Informationen wie die Notrufwählzeichenfolge und gibt an, ob ein Benutzer seinen Standort manuell eingeben muss, wenn der Standortinformationsdienst nicht automatisch einen Standort bereitstellt. Eine vollständige Definition einer Ortungsrichtlinie finden Sie unter [Definieren der Standortrichtlinie für Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

In Lync Server kann eine Ortungsrichtlinie einem Benutzer über ein Subnetz oder bei Verwendung einer Benutzerrichtlinie direkt zugewiesen werden. Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer für E9-1-1 entscheiden.

  - **Planen Sie die Aktivierung für alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**  
    Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden. Wenn Sie jedoch einem Lync Server-Netzwerkstandort eine Ortungsrichtlinie zuweisen und dem Standort Subnetze hinzufügen, können Sie die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens beschränken.

<!-- end list -->

  - **Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**  
    Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.

<!-- end list -->

  - **Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**  
    Wenn Benutzern eine globale, standortbezogene oder Pro-Benutzer-Standortrichtlinie zugewiesen ist, müssen sie möglicherweise ihren Standort manuell am Client eingeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder der Standortinformationsdienst keinen Standort finden konnte. Ausführliche Informationen finden Sie unter [Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).

