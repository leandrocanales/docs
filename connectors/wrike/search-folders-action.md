---
title: Workato connectors - Wrike Search folder action
date: 2019-06-13 18:00:00 Z
search:
    keywords: ['wrike', 'folder', 'search']
---

# Wrike - Search folder action

Folders are one of the main ways to organize and manage information on Wrike.

This action retrieves a list of folders that matches your search criteria. Only records in your Wrike instance that match all the criteria will be returned. A maximum of 100 folders can be retrieved per job.

![Search folder action](/assets/images/connectors/Wrike/search-folder-action.png)
*Search folder action*

### Input fields

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
      <th width='25%'>Input field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Custom field list</td>
      <td>
        Select a custom field to open the corresponding input field. This will be blank by default.
      </td>
    </tr>
    <tr>
      <td>Metadata</td>
      <td>
        The metadata details to use in your search. You can define metadata with a metadata source list or manually input the <code>Key</code>/<code>Value</code> pair information.
      </td>
    </tr>
    <tr>
      <td>Permalink</td>
      <td>
        The link to open the folder in a web workspace. This is only accessible if the user has the appropriate access.
      </td>
    </tr>
    <tr>
      <td>Descendants</td>
      <td>
        Select <code>Yes</code> to add all descendant folders to search scope, otherwise select <code>No</code>.
      </td>    
    </tr>
    <tr>
      <td>Retrieve deleted folders only</td>
      <td>
        Select <code>True</code> to retrieve deleted folders only, otherwise select <code>False</code>.
      </td>    
    </tr>
    <tr>
      <td>Updated date</td>
      <td>
        Retrieve folders created after this date.
      </td>
    </tr>
  </tbody>
</table>

### Output fields

<table class="unchanged rich-diff-level-one">
  <thead>
    <tr>
      <th width='25%'>Output field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Folder ID</td>
      <td>
        The ID of the folder.
      </td>
    </tr>  
    <tr>
      <td>Account ID</td>
      <td>
        The ID of the account.
      </td>
    </tr>
    <tr>
      <td>Title</td>
      <td>
        The title of the folder.
      </td>
    </tr>
    <tr>
      <td>Updated date</td>
      <td>
        The date this folder was updated.
      </td>
    </tr>
    <tr>
      <td>Created date</td>
      <td>
        The date this folder was created.
      </td>
    </tr>
    <tr>
      <td>Description</td>
      <td>
        The description of the folder. Will be blank if not specified.
      </td>
    </tr>
    <tr>
      <td>Users who share the folder</td>
      <td>
        The list of users who share the folder.
        <table>
          <tbody>
            <tr>
              <td>User ID</td>
              <td>The ID of the user who shares this folder.</td>
            </tr>
            <tr>
              <td>List size</td>
              <td>The size of the list, corresponding to the number of users retrieved.</td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    <tr>
      <td>Parent folder</td>
      <td>
        The list of parent folders of this folder.
        <table>
          <tbody>
            <tr>
              <td>Folder ID</td>
              <td>The folder ID of the parent folder.</td>
            </tr>
            <tr>
              <td>List size</td>
              <td>The size of the list, corresponding to the number of parent folders retrieved.</td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    <tr>
      <td>Child folder</td>
      <td>
        The list of child folders of this folder.
        <table>
          <tbody>
            <tr>
              <td>Folder ID</td>
              <td>The folder ID of the child folder.</td>
            </tr>
            <tr>
              <td>List size</td>
              <td>The size of the list, corresponding to the number of child folders retrieved.</td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    <tr>
      <td>Super parent folder</td>
      <td>
        The list of super parent folder to this folder.
        <table>
          <tbody>
            <tr>
              <td>Folder ID</td>
              <td>The folder ID of the super parent folder.</td>
            </tr>
            <tr>
              <td>List size</td>
              <td>The size of the list, corresponding to the number of super parent folders retrieved.</td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    <tr>
      <td>Scope</td>
      <td>
        The scope of the folder.
      </td>
    </tr>
    <tr>
      <td>Has attachments</td>
      <td>
        Indicates if the folder has attachments.
      </td>
    </tr>
    <tr>
      <td>Permalink</td>
      <td>
        The link to open the folder in a web workspace. This is only accessible if the user has the appropriate access.
      </td>
    </tr>
    <tr>
      <td>Workflow ID</td>
      <td>
        The ID of the folder workflow.
      </td>
    </tr>
    <tr>
      <td>Metadata</td>
      <td>
        The metadata of this folder. The metadata list size corresponds to the number of metadata entries retrieved.
      </td>
    </tr>
    <tr>
      <td>Project</td>
      <td>
        The project properties of this folder.
        <table>
          <tbody>
            <tr>
              <td>Author</td>
              <td>The author who created the project.</td>
            </tr>
            <tr>
              <td>Owner ID</td>
              <td>
                The list of IDs of project owners.
                <table>
                  <tbody>
                    <tr>
                      <td>User ID</td>
                      <td>The user ID of the project owner.</td>
                    </tr>
                    <tr>
                      <td>List size</td>
                      <td>The size of the list, corresponding to the number of project owners retrieved.</td>
                    </tr>
                  </tbody>
                </table>
              </td>
            </tr>
            <tr>
              <td>Status</td>
              <td>The status of the project.</td>
            </tr>
            <tr>
              <td>Start date</td>
              <td>The date this project was started.</td>
            </tr>
            <tr>
              <td>End date</td>
              <td>The date this project was ended.</td>
            </tr>
            <tr>
              <td>Created date</td>
              <td>The date this project was created.</td>
            </tr>
            <tr>
              <td>Completed date</td>
              <td>The date this project was completed.</td>
            </tr>
          </tbody>
        </table>
      </td>
    </tr>
    <tr>
      <td>Custom fields</td>
      <td>
        Includes data from custom field(s).
      </td>
    </tr>
    <tr>
      <td>List size</td>
      <td>
        The size of the list, corresponding to the number of folders retrieved.
      </td>
    </tr>
  </tbody>
</table>
