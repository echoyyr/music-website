<!--<template>-->
<!--    <div>123</div>-->
<!--</template>-->
<!--<script>-->
<!--    export default {-->

<!--    }-->
<!--</script>-->

<template>
    <div>
        <div id="container"></div>
    </div>
</template>


<script>
    import * as Three from 'three'
    import OrbitControls from 'three-orbitcontrols'
    import {OBJLoader} from 'three-obj-mtl-loader'
    import Stats from 'stats-js'


    export default {
        name: 'ThreeTest',
        data() {
            return {
                camera: null,
                scene: null,
                renderer: null,
                mesh: null,
                controls:null
            }
        },
        methods: {
            init: function() {
                let container = document.getElementById('container');

                this.camera = new Three.PerspectiveCamera(70, container.clientWidth/container.clientHeight, 0.01, 10);
                this.camera.position.z = 1;


                this.scene = new Three.Scene();

                let geometry = new Three.BoxGeometry(0.5, 0.5, 0.5);
                let material = new Three.MeshNormalMaterial();

                this.mesh = new Three.Mesh(geometry, material);
                this.scene.add(this.mesh);


                this.renderer = new Three.WebGLRenderer({antialias: true});
                this.renderer.setSize(container.clientWidth, container.clientHeight);
                this.renderer.setClearColor(0xFFFFFF);

                this.OrbitControls=new Three.OrbitControls(this.camera, this.renderer.domElement);

                container.appendChild(this.renderer.domElement);

            },
            animate: function() {
                requestAnimationFrame(this.animate);
                this.mesh.rotation.x += 0.01;
                this.mesh.rotation.y += 0.02;
                this.renderer.render(this.scene, this.camera);
            }
        },
        mounted() {
            this.init();
            this.animate()
        }
    }
</script>
<style scoped>
    #container {
        height: 100px;
        width: 100px;
    }

</style>













