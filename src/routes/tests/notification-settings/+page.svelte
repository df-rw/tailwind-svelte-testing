<script lang="ts">
    const options = [
        'New referral',
        'Referral accepted',
        'Referral reassigned',
        'Referral declined',
    ];
    const mediums = ['SMS', 'Email', 'SMS and Email'];
</script>

<table class="m-4">
    {#each options as option}
        <tr>
            <th>{option}</th>
            <td>
                <select>
                    {#each mediums as medium}
                        <option value={medium}>{medium}</option>
                    {/each}
                </select>
            </td>
        </tr>
    {/each}
</table>
