# Project Storage

Each ResHPC project has project-specific storage directories in `/group/PINetID` and `/scratch/g/PINetID`, secured with a project-specific security group. **Please note that ResHPC users do not have user scratch directories.**

For example, **jsmith** is PI for project **p12345**, with project directories `/group/jsmith/p12345` and `/scratch/g/jsmith/p12345`.

??? tip "You can easily find your available project storage and current utilization with the `mydisks` command."

    ```bash
    $ mydisks
    =====My Storage=====
     Size  Used Avail Use% File
     4.7G     0  4.7G   0% /home/user.p12345
     932G  158G  774G  17% /group/PINetID/p12345
     4.6T   62G  4.5T   2% /scratch/g/PINetID/p12345
    ```

## Encryption Requirement

Where noted below, encryption is required. This is an important step in ensuring security and integrity of restricted datasets.

## Project Directory

**Quota**: inherited from [/group](../storage/rcc-storage.md#group)  
**Snapshot**: daily @ 2PM, 7 day lifetime  
**Replication**: continuous with snapshot

Each project has a unique directory located at `/group/{PINetID}/{ProjID}`. Within each project's `/group` directory, source and results data must be kept separate. You will find the following spaces in your `/group/{PINetID}/{ProjID}` directory:

: `source` - used for protected dataset from data provider
: `results` - used for derivative results data and anything non-source

Users must keep source and results separate. Most DUAs are time limited and Research Computing may be required to delete the restricted source dataset at project closeout. Keeping source and results separate will avoid forcing Research Computing to delete all of your project data.

!!! warning "Encryption required"
    Restricted source data must be encrypted, and remain encrypted when stored in the project's group directory.

## Home Directory

**Quota**: 5 GiB  
**Snapshot**: daily @ 12PM, 7 day lifetime  
**Replication**: continuous with snapshot

Every project user account has a home directory located at `/home/{NetID}.{ProjID}`. The home directory is a requirement of hte cluster's Linux operating system. You should not store data in your home directory.

!!! warning "Restricted data"
    Storing restricted data in your home directory is prohibited.

## Scratch Directory

**Quota**: inherited from [/scratch](../storage/rcc-storage.md#scratch)  
**Purge**: files may be deleted after 180 days

Each project has a unique scratch directory located at `/scratch/g/{PINetID}/{ProjID}`. You may mix source and results files within your project scratch directory. However, you must delete all data in your scratch when your job is done.

!!! warning "Encryption required"
    Restricted source data may only be decrypted in the project's scratch directory, and only as needed for analysis. Do not leave unencrypted data in project's scratch directory. For example, if you're going on vacation, delete the unencrypted data.

--8<-- "includes/abbreviations.md"
