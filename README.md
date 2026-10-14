# Home Network Asset Inventory and Classification

> **Disclaimer:** This project was completed as part of the Google Cybersecurity Certificate (Coursera). The scenario and template come from the course. The inventory, notes, and classifications are my own documentation of the work I performed.

## Project description
I operate a small business from my home and needed an inventory of the devices connected to my home network to determine which ones hold sensitive information and need extra protection. I identified three devices (a business laptop, a network attached storage device, and a smart TV), recorded their network access, owner, and location, noted details that affect the confidentiality, integrity, and availability of the information they handle, and classified each one by sensitivity. An asset inventory is the first step of asset management: you can't protect what you haven't cataloged.

## Sensitivity Levels
| Level | Access designation | Meaning |
|---|---|---|
| **Restricted** | Need-to-know | Highest sensitivity. Compromise could cause severe harm, such as exposed business or client data |
| **Confidential** | Limited to specific users | Important information that should only be shared with approved people |
| **Internal-only** | Users on-premises | Intended for use inside the organization, with limited impact if exposed |
| **Public** | Anyone | Information that is safe to share publicly |

## Asset Inventory
Devices 1-3 were provided in the template for reference. Devices 4-6 are the ones I added.

| # | Asset | Network access | Owner | Location | Notes | Sensitivity |
|---|---|---|---|---|---|---|
| 1 | Network router | Continuous | Internet service provider (ISP) | On-premises | Has a 2.4 GHz and 5 GHz connection. All devices on the home network connect to the 5 GHz frequency. | Confidential |
| 2 | Desktop | Occasional | Homeowner | On-premises | Contains private information, like photos. | Restricted |
| 3 | Guest smartphone | Occasional | Friend | On and off-premises | Connects to my home network. | Internal-only |
| 4 | **Business laptop** | Continuous | Business owner | On and off-premises | Stores sensitive client data and financial records. Connects via Wi-Fi and uses full-disk encryption. | **Restricted** |
| 5 | **Network attached storage (NAS)** | Occasional | Homeowner | On-premises | Hardwired to the network. Stores encrypted backups of business files and personal documents. | **Confidential** |
| 6 | **Smart TV** | Continuous | Homeowner | On-premises | Connects to Wi-Fi for streaming services. Does not store business data but could act as a network entry point. | **Internal-only** |

## Classification Reasoning
- **Business laptop (Restricted):** It holds the most sensitive data in the home office: client data and financial records. Disclosure would harm clients and the business, alteration could corrupt financial records, and loss could halt operations. It is on the network continuously and leaves the premises, which adds exposure. Full-disk encryption protects the data if the laptop is lost or stolen, but it still needs the highest level of protection and need-to-know access.
- **NAS (Confidential):** It stores backups of business and personal files, so compromise would expose a lot of information. Because the backups are encrypted and the device is hardwired and only occasionally connected, access is limited to specific users rather than restricted to a need-to-know basis.
- **Smart TV (Internal-only):** It stores no business data, so a compromise would have limited direct impact. It is connected continuously over Wi-Fi, though, and could act as an entry point to the rest of the network, so it should be kept updated and ideally separated from the devices that hold sensitive data.

## Summary
I identified three devices on my home network, recorded their network access, owner, and location, and noted details that affect the confidentiality, integrity, and availability of the information they handle. I classified the business laptop as Restricted, the NAS as Confidential, and the smart TV as Internal-only, based on what an attacker could disclose, change, or destroy if each one were compromised. This inventory shows which assets need the most protection first, which is the purpose of asset management in a security plan.

## Key Takeaways
- Asset management starts with an inventory: you need a catalog of what's connected before you can protect it.
- Every connected device is a potential entry point to other assets on the network, even one that stores no sensitive data, like a smart TV.
- Classify assets by asking what could be disclosed, altered, or destroyed if they were compromised, which maps directly to confidentiality, integrity, and availability.
- Network access and location matter: a device that is always connected or travels off-premises has more exposure than one that is hardwired and used occasionally.
- Controls like full-disk encryption and encrypted backups lower the risk of a compromise but don't change how sensitive the data is.
- Higher sensitivity means stronger controls, such as encryption, restricted access, and keeping devices separate from the rest of the network.
