<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="mr40 mt20">
                    <router-link to="/list-plannogram">
                        <img src="../../assets/icons/back.svg">
                    </router-link>
                </div>
                <div>
                    <h1 class="m0">Add Plannogram</h1>
                    <p class="mt5 mb20 tc-green">Increase the visibility of promotional products in our store highlights</p>
                </div>
            </div>
            <hr class="uline-grey">
            <div class="mt50 row">
                <div class="w20">
                    <label class="form-label">Background Image</label>
                </div>
                <label for="imageInput" class="custom-input-label" :style="{ backgroundImage: previewImg ? 'url(' + previewImg + ')' : 'url(../images/input gambar.png)', backgroundSize: previewImg ? 'cover' : ''}">
                    <input
                    id="imageInput"
                    accept="image/*"
                    class="form-gambar"
                    type="file"
                    v-on:change="upload"
                    />
                </label>
            </div>
            <div class="mt50 row">
                <div class="w20">
                    <label class="form-label">Plannogram Name</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Masukkan Plannogram Name"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Broadcast Schedule</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Pilih hari"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Valid From</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Masukkan Tanggal"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">Valid Until</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Masukkan Tanggal"
                    >
                </div>
            </div>
            <div class="mt30 row">
                <div class="w20">
                    <label class="form-label">List Product</label>
                </div>
                <div class="w80">
                    <input
                        class="form-text"
                        type="text"
                        placeholder="Pilih Product"
                    >
                </div>
            </div>
            <div class="flex mt30">
                <router-link to="/list-plannogram">
                    <button class="bt-submit-green">Add Plannogram</button>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
export default {
	name: 'add-plannogram',
    data() {
        return {
            gambar: '',
            previewImg: '',
        };
    },
    methods: {
        upload: function(event) {
            const nameGambar = event.target.files[0].name;
            this.gambar = nameGambar;
            this.previewImg = URL.createObjectURL(event.target.files[0])
        },  
        
    },
}
</script>