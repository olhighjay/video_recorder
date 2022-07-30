<template>
    <div class="table-responsive-xl" style="margin-top:46.1px">
        <table class="">
        <thead>
            <tr >
            <th scope="col" class="my-table-title">Recordings</th>
            <th scope="col" class="my-table-title" colspan="3">Title</th>
            <th scope="col" style="width:10%"></th>
            <th scope="col" class="my-table-title">Views</th>
            <th scope="col" class="my-table-title">Size</th>
            <th scope="col" class="my-table-title">Last Modified</th>
            <th scope="col" class="my-table-title"></th>
            </tr>
        </thead>
        <tbody>
            <tr>
            <td style="width:13%; ">
                <img alt="Profile Image" src="../assets/profile.jpg" class="table-profile-image">
            </td>
            <td style="width:30%" colspan="3">
                <span class="row-col-txt">Getting it right the first time </span> <br />
                <span class="row-col-subtxt">The Video description is shown here if the user has added it. </span>
            </td>
            <td style="width:10%">
            </td>
            <td>424</td>
            <td>923 KB</td>
            <td>3 months ago</td>
            <td><i class="fa fa-ellipsis-h"></i></td>
            </tr>
            <tr>
            <td style="width:13%; ">
                <img alt="Profile Image" src="../assets/profile.jpg" class="table-profile-image">
            </td>
            <td style="width:30%" colspan="3">
                <span class="row-col-txt">Getting it right the first time </span> <br />
                <span class="row-col-subtxt">The Video description is shown here if the user has added it. </span>
            </td>
            <td style="width:10%">
            </td>
            <td>424</td>
            <td>923 KB</td>
            <td>3 months ago</td>
            <td><i class="fa fa-ellipsis-h"></i></td>
            </tr>
            <tr>
            <td style="width:13%; ">
                <img alt="Profile Image" src="../assets/profile.jpg" class="table-profile-image">
            </td>
            <td style="width:30%" colspan="3">
                <span class="row-col-txt">Getting it right the first time </span> <br />
                <span class="row-col-subtxt">The Video description is shown here if the user has added it. </span>
            </td>
            <td style="width:10%">
            </td>
            <td>424</td>
            <td>923 KB</td>
            <td>3 months ago</td>
            <td><i class="fa fa-ellipsis-h"></i></td>
            </tr>
            <tr>
            <td style="width:13%; ">
                <img alt="Profile Image" src="../assets/profile.jpg" class="table-profile-image">
            </td>
            <td style="width:30%" colspan="3">
                <span class="row-col-txt">Getting it right the first time </span> <br />
                <span class="row-col-subtxt">The Video description is shown here if the user has added it. </span>
            </td>
            <td style="width:10%">
            </td>
            <td>424</td>
            <td>923 KB</td>
            <td>3 months ago</td>
            <td><i class="fa fa-ellipsis-h"></i></td>
            </tr>
            <tr>
            <td style="width:13%; ">
                <img alt="Profile Image" src="../assets/profile.jpg" class="table-profile-image">
            </td>
            <td style="width:30%" colspan="3">
                <span class="row-col-txt">Getting it right the first time </span> <br />
                <span class="row-col-subtxt">The Video description is shown here if the user has added it. </span>
            </td>
            <td style="width:10%">
            </td>
            <td>424</td>
            <td>923 KB</td>
            <td>3 months ago</td>
            <td><i class="fa fa-ellipsis-h"></i></td>
            </tr>
        </tbody>
        </table>
    </div>
</template>

<script>
import moment from 'moment'
import db from '../../db.json'
export default {
    name: 'DataTable',
    methods:{
        convertDay() {
            console.log(db);
            console.log(moment("2022-04-29T09:37:35+02:00").fromNow());
        }
    },
    created(){
        this.convertDay();
    }
}
</script>

<style>
    table  {
  border-spacing: 300px !important;
}
th, td {
  padding: 10px;
}
.my-table-title {
  text-align: left;
  font: normal normal medium 18px/27px Poppins;
  letter-spacing: 0px;
  color: #21455E;
}
.row-col-txt {
  color:#21455E
}
.row-col-subtxt {
  text-align: left;
  font: normal normal normal 12px/18px Poppins;
  letter-spacing: 0px;
  color: #A3BAC6;
  line-height: 0;
}
.table-profile-image {
  width:100%; 
  height:55px; 
  border-radius:5px;
}
</style>