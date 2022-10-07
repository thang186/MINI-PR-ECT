void f_searchName(char* name)
{
    int i = 0;
    fflush(stdin);
    f_redundant(name);
    f_firstupper(name);	// correct the format of the name you want to find
    struct node* temp;
    temp = top;
    while (temp != NULL)
    {
        if (strstr(temp->info.name, name) != NULL) // if the string name exist in the element, then show all information of that element
        {
            printf("\n - Name : %s", temp->info.name);
            printf("\n - ID : %s", temp->info.id);
            printf("\n - Year : %d", temp->info.year);
            printf("\n - Hometown : %s", temp->info.address);
            printf("\n - Faculity : %s", temp->info.faculity);
            printf("\n - Major : %s", temp->info.major);
            printf("\n - Entry point : %0.2f", temp->info.entry);
            printf("\n - Accumulated point : %0.2f", temp->info.accumulation);
            //fflush(stdin);
            i++;
        }
        temp = temp->next;
    }
    if (i == 0)
        printf("\n\t\t\t\t(ToT) No result for the name you want (ToT)\n");
    else
        printf("\n\n\t\t\t\t(^u^) This is the end of searching ! (^u^)");
}
