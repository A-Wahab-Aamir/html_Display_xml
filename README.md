# html_Display_xml


1) FETCH DATA FROM XML FILE BY J QUERY
2) DATA TABLE  (https://datatables.net/) J QUERY PLUGIN
3) JQUERY SCRIPT 
---------------------------------------------------------------
<script>
    $(document).ready(function(){
        $.get("catalog.xml", function(res){
            $(res).find("CD").each(function(){
                var data=document.getElementById('tbody');
                var title=$(this).find("TITLE").text();
                var art=$(this).find("ARTIST").text();
                var count=$(this).find("COUNTRY").text();
                var comp=$(this).find("COMPANY").text();
                var price=$(this).find("PRICE").text();
                var year=$(this).find("YEAR").text();
                data.innerHTML +=`
               
                <tr>
                        <td>${title}</td>
                        <td>${art}</td>
                        <td>${count}</td>
                        <td>${comp}</td>
                        <td>${price}</td>
                        <td>${year}</td>
                    </tr>
                `
               
            })
        $('#mytable').DataTable()
        })
    })
</script>



File export (MAKE BUTTONS USINGJ QUERY PLUGINS)
 link: https://datatables.net/extensions/buttons/examples/initialisation/export.html


Copy to clipboard
Save as Excel (XLSX)
Save as CSV
Save as PDF
Display a print view
-----------------------------
ALL SCRIPT TAGS FOR TABLE DATA BUTTON 


<script src="https://code.jquery.com/jquery-3.7.0.min.js&quot; integrity="sha256-2Pmvv0kuTBOenSvLm6bvfBSSHrUJ+3A7x6P5Ebd07/g=" crossorigin="anonymous"></script>
<script src="https://cdn.datatables.net/1.13.4/js/jquery.dataTables.min.js"></script&gt;
<script src="https://cdn.datatables.net/buttons/2.3.6/js/dataTables.buttons.min.js"></script&gt;
<script src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script&gt;
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script&gt;
<script src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script&gt;
<script src="https://cdn.datatables.net/buttons/2.3.6/js/buttons.html5.min.js"></script&gt;
<script src="https://cdn.datatables.net/buttons/2.3.6/js/buttons.print.min.js"></script&gt;
<script>

$(document).ready(function(){
    $.get('index.xml', function(res){
        $(res).find('student').each(function(){
            var id=$(this).find('id').text();
            var name=$(this).find('name').text();
            var clas=$(this).find('class').text();
            document.getElementById('tbody').innerHTML +=`
    <tr>
        <td>${id}</td>
        <td>${name}</td>
        <td>${clas}</td>
    </tr>
            `

           
        })
        $('#example').DataTable( {
            dom: 'Bfrtip',
            buttons: [
                'copy', 'csv', 'excel', 'pdf', 'print'
            ]
    } );
       
    })
})

</script>
