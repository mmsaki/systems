# 5. Durability

Once data is successfully submitted to the system, it is not lost

> E.g. We upload a photo to instagram, and once we receive information about a successful upload we can be sure that it will not disappear from the system.

**How do systems ensure durability?**

> By creating and maintaing **multiple copies** of data

1. [Backup](#1-backup)
1. RAID
1. Replication

## 1. Backup

Copy data elsewhere periodically (e.g once a day) from a non-volatile storage, such as disk

There are three popular strategies to crate backups:

1. **full** backup
   > Always create a full copy of data
   1. If the primary storage data fails, we initate a disaster recovery process
   1. We restore data from the most recent backup
   1. **pros**: short restoration time
1. **differential** backup
1. **incremental** backup
