---
title: 'Lync Server 2013: Bereitstellen von IP-Adresstypen auf einem Edgeserver'
TOCTitle: Bereitstellen von IP-Adresstypen auf einem Edgeserver
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204984(v=OCS.15)
ms:contentKeyID: 49294337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen von IP-Adresstypen auf einem Edgeserver für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-14_

Führen Sie mithilfe des Topologie-Generators die folgenden Schritte aus, um IP-Adresstypen auf einem Edgeserver bereitzustellen.

## So stellen Sie IP-Adresstypen auf dem Edgeserver bereit

1.  Klicken Sie im Topologie-Generator unter **Edgepools** mit der rechten Maustaste auf den Server innerhalb eines Pools, und wählen Sie dann **Eigenschaften bearbeiten** aus. (Sie können auch den Server auswählen und dann im Menü **Aktion** auf **Eigenschaften bearbeiten** klicken.)

2.  Wählen Sie im Fenster **Eigenschaften bearbeiten** die IP-Adresskonfiguration, die Sie verwenden möchten. In den folgenden Abbildungen wird eine Dualstapelkonfiguration für die interne und die externe Schnittstelle dargestellt.
    
    **Interne Dualstapelschnittstelle für Edge Server**
    
    ![Allgemeine Lync Server-Eigenschaften (Seite)](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Allgemeine Lync Server-Eigenschaften (Seite)")
    
    **Externe Dualstapelschnittstelle für Edge Server**
    
    ![Lync Server-Konfiguration für nächsten Hop/extern (Seite)](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server-Konfiguration für nächsten Hop/extern (Seite)")

3.  Für jeden Adresstyp, den Sie auswählen, müssen Sie die geeigneten internen und externen Adressen auswählen.

