---
title: Edgecomputereinstellungen – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.EdgeMachineSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 747456dd-d237-44e6-9e64-63b0e7212a08
description: 'Führen Sie zum Bearbeiten der Eigenschaften eines Servers in einem Edgeserverpool die folgenden Schritte aus:'
---

# <a name="edge-machine-settings-expander"></a>Edgecomputereinstellungen – Erweiterung
 
Führen Sie zum Bearbeiten der Eigenschaften eines Servers in einem Edgeserverpool die folgenden Schritte aus:
  
Der interne Name oder vollqualifizierte Domänenname (FQDN) kann durch Bearbeiten des vollqualifizierten Domänennamens geändert werden. Der vollqualifizierte Domänenname muss dem DNS-Hosteintrag (A) und dem Antragstellernamen des Zertifikats entsprechen, das dem Server für die interne Edge-Netzwerkschnittstelle zugewiesen ist. Der Wert von **Interne IP-Adresse** gibt die IP-Adresse an, die der als internes Netzwerk definierten Netzwerkschnittstelle relativ zum Entwurf des Umkreisnetzwerks zugewiesen ist.
  
In den folgenden drei Abschnitten des Dialogfelds werden die IP-Adressen für die externe Konfiguration dieses Edgeservers bestimmt. Die Möglichkeit zur Änderung der IP-Adressen wird von der Einstellung **Separaten FQDN und IP-Adresse für Webkonferenzen und A/V aktivieren** im Dialogfeld "Einstellungen" auf Edgeserverpool-Ebene bestimmt.
  
## <a name="sip-access"></a>SIP-Zugriff

Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für den SIP-Zugriff (Session Initiation Protocol) zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.
  
> [!NOTE]
> Wenn die Einstellung **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren** auf der Seite mit den Pooleinstellungen aktiviert ist, kann nur die IP-Adresse für den SIP-Zugriff bearbeitet werden.
  
## <a name="web-conferencing"></a>Webkonferenzen

Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für Webkonferenzen zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.
  
## <a name="audiovideo"></a>Audio/Video

Dient zum Bearbeiten der externen IP-Adresse, die der Netzwerkschnittstelle für Audio/Video (A/V) zugewiesen ist. Diese IP-Adresse kann entweder eine öffentliche IP-Adresse oder eine Adresse im privaten IP-Adressbereich sein.
  
Die Einstellung **Für NAT aktivierte verwendete öffentliche IP-Adresse** ist die von der externen Schnittstelle für entweder die A/V-Netzwerkschnittstelle oder den Edgeserver im Allgemeinen verwendete öffentliche IP-Adresse. Wenn die Einstellung **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren** aktiviert ist, wird diese IP-Adresse für alle drei externen Schnittstellen verwendet.
  

